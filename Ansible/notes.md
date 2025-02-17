### **Interactive Ansible Tutorial: From Basics to Advanced**

This tutorial guides you through Ansible fundamentals with hands-on examples. Follow each step, run commands, and observe results. Let’s start!

---

#### **1. Installation**
Install Ansible on your control node (machine where Ansible runs).

**Debian/Ubuntu:**
```bash
sudo apt update && sudo apt install ansible -y
```

**RHEL/CentOS:**
```bash
sudo dnf install ansible -y
```

**macOS (via pip):**
```bash
python3 -m pip install ansible
```

**Verify Installation:**
```bash
ansible --version
```

---

#### **2. Inventory Setup**
Ansible manages nodes listed in an **inventory file** (default: `/etc/ansible/hosts`). Create a local `inventory.ini`:

```ini
[webservers]
server1 ansible_host=192.168.1.10
server2 ansible_host=192.168.1.11

[databases]
db1 ansible_host=192.168.1.20

[all:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=~/.ssh/id_rsa
```

**View Parsed Inventory:**
```bash
ansible-inventory -i inventory.ini --graph
```

---

#### **3. Ad-Hoc Commands**
Run one-off tasks using `ansible` CLI.

**Ping All Servers:**
```bash
ansible -i inventory.ini all -m ping
```

**Check Uptime on Webservers:**
```bash
ansible -i inventory.ini webservers -a "uptime"
```

**Install Nginx on Databases (with sudo):**
```bash
ansible -i inventory.ini databases -m apt -a "name=nginx state=present" --become
```

**Exercise:** Replace `uptime` with `free -m` to check memory usage on `webservers`.

---

#### **4. Playbooks**
Playbooks are YAML files defining automation workflows.

**Create `apache.yml`:**
```yaml
---
- name: Install and Start Apache
  hosts: webservers
  become: yes
  tasks:
    - name: Install Apache
      apt:
        name: apache2
        state: present

    - name: Start Apache Service
      service:
        name: apache2
        state: started
        enabled: yes
```

**Run the Playbook:**
```bash
ansible-playbook -i inventory.ini apache.yml
```

**Exercise:** Modify the playbook to install `nginx` instead.

---

#### **5. Variables**
Variables customize behavior. Define them in playbooks, inventories, or files.

**Using Variables in a Playbook:**
```yaml
- hosts: webservers
  vars:
    http_port: 80
  tasks:
    - debug:
        msg: "Web server port is {{ http_port }}"
```

**Variable File (`vars.yml`):**
```yaml
package_name: nginx
```

**Include Variables in Playbook:**
```yaml
- hosts: webservers
  vars_files:
    - vars.yml
  tasks:
    - apt:
        name: "{{ package_name }}"
```

**Exercise:** Add a variable `service_name` and use it in the `service` module.

---

#### **6. Roles**
Roles organize playbooks into reusable components.

**Create a Role:**
```bash
ansible-galaxy init roles/webserver
```

**Directory Structure:**
```
roles/webserver/
├── tasks
│   └── main.yml
├── handlers
│   └── main.yml
└── vars
    └── main.yml
```

**Use the Role in `site.yml`:**
```yaml
- hosts: webservers
  roles:
    - webserver
```

**Exercise:** Create a role `database` to install MySQL.

---

#### **7. Handlers**
Handlers trigger actions only when notified by tasks (e.g., restart services).

**Example:**
```yaml
tasks:
  - name: Update Apache Config
    copy:
      src: apache.conf
      dest: /etc/apache2/apache.conf
    notify: Restart Apache

handlers:
  - name: Restart Apache
    service:
      name: apache2
      state: restarted
```

**Exercise:** Add a handler to reload Nginx after a config change.

---

#### **8. Templates**
Use Jinja2 templates to dynamically generate files.

**Create `index.html.j2`:**
```html
<html>
  <body>
    <h1>Welcome to {{ ansible_hostname }}!</h1>
  </body>
</html>
```

**Deploy the Template:**
```yaml
- name: Deploy Index Page
  template:
    src: index.html.j2
    dest: /var/www/html/index.html
```

**Exercise:** Create a template for Nginx’s `server_name`.

---

#### **9. Ansible Vault**
Encrypt sensitive data (e.g., passwords).

**Create Encrypted File:**
```bash
ansible-vault create secrets.yml
```

**Edit Encrypted File:**
```bash
ansible-vault edit secrets.yml
```

**Use Vault in Playbook:**
```yaml
- hosts: databases
  vars_files:
    - secrets.yml
  tasks:
    - debug:
        var: db_password
```

**Run Playbook with Vault:**
```bash
ansible-playbook --ask-vault-pass deploy_db.yml
```

**Exercise:** Encrypt a variable file containing `api_key: "12345"`.

---

#### **10. Best Practices**
- **Use Roles:** Organize code into roles (e.g., `webserver`, `database`).
- **Group Variables:** Store variables in `group_vars/` or `host_vars/`.
- **Tagging:** Assign tags to tasks for selective execution.
  ```yaml
  tasks:
    - name: Install Dependencies
      apt:
        name: "{{ item }}"
      loop: [git, curl]
      tags: install
  ```
- **Linting:** Check playbook syntax with `ansible-lint`.
- **Version Control:** Track changes with Git.

---

#### **Sample Project: Deploy a Web App**
**Structure:**
```
project/
├── inventory.ini
├── site.yml
├── group_vars/
│   └── webservers.yml
├── roles/
│   ├── common/
│   ├── webserver/
│   └── database/
└── vault.yml
```

**Run the Full Setup:**
```bash
ansible-playbook -i inventory.ini site.yml --ask-vault-pass
```

---

**Next Steps:**
- Explore Ansible Galaxy for pre-built roles.
- Learn about dynamic inventories (AWS, Docker).
- Experiment with modules like `docker_container`, `aws_ec2`.

**Official Docs:** [Ansible Documentation](https://docs.ansible.com/)

By following this guide, you’ve automated server setup, configuration, and deployment! Practice each concept to solidify your understanding.
