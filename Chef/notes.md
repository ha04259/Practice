### **Chef Automation Tutorial: Comprehensive Guide with Examples**

Chef is a powerful infrastructure automation tool that allows you to manage configurations, deploy applications, and automate workflows using code (Infrastructure as Code, IaC). This tutorial covers core concepts, setup, and practical examples.

---

### **1. Chef Components**
- **Chef Workstation**: Your local machine where you write and test code.
- **Chef Server**: Central hub storing configurations, cookbooks, and node data.
- **Nodes**: Servers managed by Chef (e.g., web servers, databases).
- **Cookbooks**: Reusable units of configuration (recipes, templates, files).

---

### **2. Installation & Setup**
#### **Install Chef Workstation**
```bash
# Linux (Debian/Ubuntu)
wget https://packages.chef.io/files/stable/chef-workstation/23.10.1038/ubuntu/20.04/chef-workstation_23.10.1038-1_amd64.deb
sudo dpkg -i chef-workstation_*.deb

# macOS
brew install chef-workstation
```

#### **Set Up Chef Server**
Use [Hosted Chef](https://manage.chef.io) (free tier) or install Chef Infra Server.

---

### **3. Key Concepts & Examples**

#### **A. Resources**
Resources define the desired state of a system component (e.g., install a package).

**Example: Install Nginx**
```ruby
package 'nginx' do
  action :install
end

service 'nginx' do
  action [:enable, :start]
end
```

#### **B. Recipes**
Recipes are collections of resources. Save this in `cookbooks/my_cookbook/recipes/default.rb`:
```ruby
package 'nginx'

service 'nginx' do
  action [:enable, :start]
end

file '/var/www/html/index.html' do
  content 'Hello from Chef!'
  mode '0644'
end
```

#### **C. Cookbooks**
Generate a cookbook structure:
```bash
chef generate cookbook my_cookbook
```
Directory structure:
```
my_cookbook/
  ├── recipes/
  │   └── default.rb
  ├── templates/
  ├── attributes/
  └── metadata.rb
```

#### **D. Templates**
Use ERB templates for dynamic files.

**Example: Template for Nginx Config**
1. Create `templates/default/nginx.conf.erb`:
   ```erb
   server {
     listen 80;
     server_name <%= @server_name %>;
     root <%= @web_root %>;
   }
   ```
2. Use the template in a recipe:
   ```ruby
   template '/etc/nginx/sites-available/default' do
     source 'nginx.conf.erb'
     variables(
       server_name: 'example.com',
       web_root: '/var/www/html'
     )
     notifies :reload, 'service[nginx]'
   end
   ```

#### **E. Attributes**
Define variables in `attributes/default.rb`:
```ruby
default['my_cookbook']['package'] = 'nginx'
default['my_cookbook']['port'] = 80
```

Use in a recipe:
```ruby
package node['my_cookbook']['package']
```

#### **F. Roles**
Define roles (e.g., `roles/web_server.rb`):
```ruby
name "web_server"
description "Role for web servers"
run_list "recipe[my_cookbook]"
default_attributes 'my_cookbook' => { 'port' => 8080 }
```

#### **G. Data Bags**
Store secrets (e.g., API keys).
1. Create a data bag:
   ```bash
   knife data bag create credentials production_key --secret-file=encrypted_data_bag_secret
   ```
2. Use in a recipe:
   ```ruby
   db_creds = data_bag_item('credentials', 'production_key')
   ```

#### **H. Knife Commands**
- Bootstrap a node:
  ```bash
  knife bootstrap <node-ip> -N node1 -x user -P password --sudo
  ```
- Upload a cookbook:
  ```bash
  knife cookbook upload my_cookbook
  ```

---

### **4. Testing with Test Kitchen**
Test cookbooks locally using Vagrant/VirtualBox.

1. Configure `.kitchen.yml`:
   ```yaml
   driver:
     name: vagrant
   provisioner:
     name: chef_zero
   platforms:
     - name: ubuntu-20.04
   suites:
     - name: default
       run_list: recipe[my_cookbook::default]
   ```
2. Run tests:
   ```bash
   kitchen converge  # Deploy the cookbook
   kitchen verify    # Run InSpec tests
   ```

---

### **5. Example Workflow**
1. Create a cookbook:
   ```bash
   chef generate cookbook deploy_app
   ```
2. Write recipes to install dependencies, deploy code, and start services.
3. Test locally with Test Kitchen.
4. Upload to Chef Server:
   ```bash
   knife cookbook upload deploy_app
   ```
5. Apply to nodes via roles or run lists.

---

### **6. Best Practices**
- **Version Control**: Track cookbooks in Git.
- **Test Recipes**: Use InSpec for validation.
- **Small Cookbooks**: Keep them focused (e.g., `apache`, `mysql`).
- **Use Community Cookbooks**: Explore [Chef Supermarket](https://supermarket.chef.io).

---

### **7. Further Learning**
- [Chef Documentation](https://docs.chef.io)
- [Learn Chef Rally](https://learn.chef.io)
- **Books**: _Chef Infrastructure Automation_ by John Ewart.

By mastering these concepts, you can automate complex infrastructure tasks efficiently! 🚀

Here’s a step-by-step guide to creating a Chef cookbook, performing syntax checks, dry-run tests, and deploying it to a node. Includes all required commands:

---

### **1. Create a Cookbook**
Generate a new cookbook structure using `chef generate`:

```bash
chef generate cookbook my_cookbook
cd my_cookbook
```

---

### **2. Write a Recipe**
Edit the default recipe (`recipes/default.rb`). Example:  
```ruby
# Install Apache and start the service
package 'apache2' do
  action :install
end

service 'apache2' do
  action [:enable, :start]
end

# Create a sample HTML file
file '/var/www/html/index.html' do
  content '<h1>Hello from Chef!</h1>'
  mode '0644'
end
```

---

### **3. Syntax & Style Checks**
#### **Lint the Cookbook**  
Check for Ruby/Chef syntax errors and best practices:  
```bash
cookstyle .
```

#### **Validate Metadata**  
Ensure `metadata.rb` is valid:  
```bash
knife cookbook metadata -o .
```

---

### **4. Dry-Run (Why-Run) Test**
Simulate the Chef run without making actual changes:  
```bash
# Run in local mode (replace NODE_NAME with your node's name)
chef-client --why-run --local-mode --override-runlist 'my_cookbook'
```

---

### **5. Test with Test Kitchen**
Test the cookbook locally using Vagrant/VM.

#### **Configure `.kitchen.yml`**  
Update the file to:  
```yaml
driver:
  name: vagrant

provisioner:
  name: chef_zero

platforms:
  - name: ubuntu-20.04

suites:
  - name: default
    run_list:
      - recipe[my_cookbook::default]
```

#### **Run Tests**  
```bash
# Start the VM and apply the cookbook
kitchen converge

# Verify the setup (optional: write InSpec tests in test/integration/default/)
kitchen verify

# Destroy the VM after testing
kitchen destroy
```

---

### **6. Deploy to Nodes**
#### **Upload the Cookbook to Chef Server**  
```bash
knife cookbook upload my_cookbook
```

#### **Bootstrap a Node (if new)**  
Replace `<NODE_IP>`, `<USER>`, and `<PASSWORD>` with your node’s details:  
```bash
knife bootstrap <NODE_IP> -N node1 -x <USER> -P <PASSWORD> --sudo --run-list 'recipe[my_cookbook]'
```

#### **Apply to Existing Node**  
Add the cookbook to the node’s run list:  
```bash
knife node run_list add <NODE_NAME> 'recipe[my_cookbook]'
```

Trigger a Chef Client run on the node:  
```bash
# SSH into the node and run:
sudo chef-client
```

---

### **7. Example Workflow**
1. **Create the cookbook**:  
   ```bash
   chef generate cookbook deploy_webapp
   ```

2. **Write recipes and test locally**:  
   ```bash
   cookstyle .
   chef-client --why-run --local-mode
   ```

3. **Test in Kitchen**:  
   ```bash
   kitchen converge && kitchen verify
   ```

4. **Deploy**:  
   ```bash
   knife cookbook upload deploy_webapp
   knife node run_list add web_server 'recipe[deploy_webapp]'
   ```

---

### **Key Commands Summary**
| Task                | Command                                                                 |
|---------------------|-------------------------------------------------------------------------|
| Create Cookbook     | `chef generate cookbook COOKBOOK_NAME`                                  |
| Lint                | `cookstyle .`                                                          |
| Dry Run             | `chef-client --why-run --local-mode --override-runlist 'COOKBOOK_NAME'`|
| Test Kitchen Deploy | `kitchen converge`                                                     |
| Upload Cookbook     | `knife cookbook upload COOKBOOK_NAME`                                  |
| Bootstrap Node      | `knife bootstrap NODE_IP -N NODE_NAME -x USER -P PASSWORD --sudo`      |

---

