

---

### **1. Taiga (Agile Project Management)**
1. **Q:** What is Taiga primarily used for?  
   **A:** Agile project management (supports Scrum, Kanban, and hybrid workflows).

2. **Q:** What is an "Epic" in Taiga?  
   **A:** A large user story that spans multiple sprints or teams.

3. **Q:** How does Taiga differ from Jira?  
   **A:** Taiga is open-source, simpler UX, and focuses on Agile/Scrum/Kanban with fewer enterprise features.

4. **Q:** What is a "User Story" in Taiga?  
   **A:** A description of a feature from an end-user perspective, broken into tasks.

5. **Q:** How do you create a sprint backlog in Taiga?  
   **A:** Define user stories, prioritize them, and assign to a sprint in the backlog section.

6. **Q:** What is the purpose of the "Kanban board" in Taiga?  
   **A:** Visualize workflow stages (e.g., To Do, In Progress, Done) for continuous delivery.

7. **Q:** How do you track progress in a Taiga project?  
   **A:** Burn-down charts, sprint progress bars, and cumulative flow diagrams.

8. **Q:** What is a "Task" in Taiga?  
   **A:** A smaller unit of work under a user story, assigned to team members.

9. **Q:** How does Taiga handle issue tracking?  
   **A:** Customizable issues (bugs, questions) linked to user stories or tasks.

10. **Q:** What is the role of "Points" in Taiga?  
    **A:** Estimate effort for user stories (e.g., Fibonacci sequence).

11. **Q:** How do you integrate Taiga with Git?  
    **A:** Use webhooks to connect Taiga to repositories (e.g., GitHub, GitLab).

12. **Q:** What is a "Milestone" in Taiga?  
    **A:** A target date for completing a set of user stories (often a sprint deadline).

13. **Q:** How do you assign roles in Taiga?  
    **A:** Admins assign roles (Owner, Member, Viewer) via project settings.

14. **Q:** What is a "Swimlane" in Taiga Kanban?  
    **A:** Horizontal lanes to categorize tasks (e.g., by team or priority).

15. **Q:** How does Taiga support Agile metrics?  
    **A:** Provides velocity charts, lead time, and cycle time reports.

16. **Q:** What is the difference between "Backlog" and "Sprint" in Taiga?  
    **A:** Backlog holds unplanned stories; Sprint is a time-boxed iteration of work.

17. **Q:** How do you export data from Taiga?  
    **A:** Use CSV/JSON exports via the "Admin" panel.

18. **Q:** What is a "Definition of Done" (DoD) in Taiga?  
    **A:** Criteria a task must meet to be marked complete (e.g., tested, documented).

19. **Q:** How do you customize workflows in Taiga?  
    **A:** Modify Kanban columns or Scrum workflows in project settings.

20. **Q:** What is Taiga’s "Wiki" used for?  
    **A:** Collaborative documentation space for project requirements, guidelines, etc.

---

### **2. Kubernetes**
1. **Q:** What is a Pod in Kubernetes?  
   **A:** The smallest deployable unit, hosting one or more containers sharing resources.

2. **Q:** How do you scale a Deployment to 5 replicas?  
   **A:** `kubectl scale deployment <name> --replicas=5`.

3. **Q:** What is the role of the Kubernetes Scheduler?  
   **A:** Assigns Pods to nodes based on resource availability and constraints.

4. **Q:** Explain the difference between a Deployment and a StatefulSet.  
   **A:** Deployments manage stateless apps; StatefulSets handle stateful apps with stable network identities.

5. **Q:** How do you expose a Pod to external traffic?  
   **A:** Create a Service of type `NodePort` or `LoadBalancer`.

6. **Q:** What is a ConfigMap?  
   **A:** Stores non-sensitive configuration data (e.g., environment variables) for Pods.

7. **Q:** How do you check Pod logs?  
   **A:** `kubectl logs <pod-name>`.

8. **Q:** What is an Ingress Controller?  
   **A:** Manages external access to services (e.g., routing HTTP/HTTPS traffic).

9. **Q:** How does Kubernetes ensure high availability?  
   **A:** ReplicaSets, self-healing (restarts failed Pods), and multi-node clusters.

10. **Q:** What is `kubectl apply -f <file>` used for?  
    **A:** Applies configuration from a YAML/JSON file to create/update resources.

11. **Q:** What is a PersistentVolume (PV)?  
    **A:** Storage resource provisioned for Pods to retain data beyond their lifecycle.

12. **Q:** How do you update a Deployment without downtime?  
    **A:** Use rolling updates: `kubectl set image deployment/<name> <container>=<new-image>`.

13. **Q:** What is a Namespace?  
    **A:** Logical grouping of resources (e.g., separating dev/prod environments).

14. **Q:** How do you troubleshoot a Pod stuck in "Pending" state?  
    **A:** Check resource quotas, node availability, and scheduling constraints.

15. **Q:** What is `kubelet`?  
    **A:** Node agent ensuring containers are running in a Pod.

16. **Q:** What is the difference between `kubectl exec` and `kubectl attach`?  
    **A:** `exec` runs a command in a container; `attach` connects to a running process.

17. **Q:** How do you secure Kubernetes Secrets?  
    **A:** Store them encrypted at rest, limit RBAC access, and avoid hardcoding.

18. **Q:** What is Helm?  
    **A:** Package manager for Kubernetes (deploys charts—preconfigured apps).

19. **Q:** What is a DaemonSet?  
    **A:** Ensures all nodes run a copy of a Pod (e.g., logging agents).

20. **Q:** How do you drain a node for maintenance?  
    **A:** `kubectl drain <node-name> --ignore-daemonsets`.

---

### **3. Linux**
1. **Q:** How do you list all files (including hidden) in a directory?  
   **A:** `ls -a`.

2. **Q:** What does `chmod 755 <file>` do?  
   **A:** Grants owner rwx, group/others rx.

3. **Q:** How to find a process using port 8080?  
   **A:** `sudo lsof -i :8080` or `netstat -tulpn | grep 8080`.

4. **Q:** What is the purpose of `/etc/passwd`?  
   **A:** Stores user account information (e.g., UID, home directory).

5. **Q:** How to add a user to a group?  
   **A:** `usermod -aG <group> <user>`.

6. **Q:** What is the difference between `kill` and `kill -9`?  
   **A:** `kill` sends SIGTERM (graceful termination); `kill -9` sends SIGKILL (forceful).

7. **Q:** How to check disk space?  
   **A:** `df -h`.

8. **Q:** What does `grep "error" /var/log/syslog` do?  
   **A:** Searches for "error" in the syslog file.

9. **Q:** How to schedule a cron job to run daily at 2 AM?  
   **A:** `0 2 * * * /path/to/script.sh`.

10. **Q:** What is the difference between `su` and `sudo`?  
    **A:** `su` switches user (needs target user’s password); `sudo` runs commands as root (uses own password).

11. **Q:** How to set an environment variable permanently?  
    **A:** Add it to `~/.bashrc` or `/etc/environment`.

12. **Q:** What is the purpose of `rsync`?  
    **A:** Efficiently sync files/directories (supports delta transfers).

13. **Q:** How to check running processes?  
    **A:** `ps aux` or `top`.

14. **Q:** What does `umask 022` do?  
    **A:** Sets default file permissions to 755 (dirs) and 644 (files).

15. **Q:** How to compress a directory using tar?  
    **A:** `tar -czvf archive.tar.gz /path/to/dir`.

16. **Q:** What is `ssh-keygen` used for?  
    **A:** Generates SSH key pairs (public/private keys).

17. **Q:** How to check kernel version?  
    **A:** `uname -r`.

18. **Q:** What is the purpose of `iptables`?  
    **A:** Configures firewall rules (packet filtering/NAT).

19. **Q:** How to search for a package in apt?  
    **A:** `apt search <package-name>`.

20. **Q:** What does `systemctl restart nginx` do?  
    **A:** Restarts the Nginx service.

---

### **4. Network Monitoring**
1. **Q:** What is SNMP used for?  
   **A:** Collects device metrics (e.g., routers, servers) via OIDs.

2. **Q:** What is the difference between ICMP and TCP?  
   **A:** ICMP is connectionless (ping); TCP is connection-oriented (HTTP, SSH).

3. **Q:** Name a tool for packet sniffing.  
   **A:** Wireshark or tcpdump.

4. **Q:** What is latency?  
   **A:** Time taken for data to travel between source and destination.

5. **Q:** How does Nagios monitor hosts?  
   **A:** Uses plugins to check services (HTTP, CPU) and alerts on thresholds.

6. **Q:** What is NetFlow?  
   **A:** Cisco protocol for collecting IP traffic statistics (source/destination, volume).

7. **Q:** What is Prometheus used for?  
   **A:** Monitoring and alerting toolkit (time-series data, often with Grafana).

8. **Q:** How to check open ports on a Linux server?  
   **A:** `netstat -tulpn` or `ss -tulpn`.

9. **Q:** What is the purpose of a "heartbeat" in monitoring?  
   **A:** Checks if a service is alive by periodic signals.

10. **Q:** What is the difference between active and passive monitoring?  
    **A:** Active sends probes (e.g., ping); passive analyzes existing traffic (e.g., logs).

11. **Q:** What is a "false positive" in alerting?  
    **A:** Alert triggered when no actual issue exists.

12. **Q:** How does Zabbix collect data?  
    **A:** Agents, SNMP, or HTTP checks.

13. **Q:** What is "bandwidth utilization"?  
    **A:** Percentage of network capacity used over time.

14. **Q:** What is the role of a "syslog server"?  
    **A:** Centralizes log collection from multiple devices.

15. **Q:** How to simulate network latency for testing?  
    **A:** Use `tc` (Traffic Control) on Linux.

16. **Q:** What is APM (Application Performance Monitoring)?  
    **A:** Tracks app performance metrics (response time, error rates).

17. **Q:** What is the purpose of a "canary deployment" in monitoring?  
    **A:** Roll out changes to a small group to detect issues early.

18. **Q:** How to monitor Docker containers?  
    **A:** Tools like cAdvisor, Prometheus, or Docker stats.

19. **Q:** What is "jitter" in networking?  
    **A:** Variation in packet delay (affects real-time apps like VoIP).

20. **Q:** How to check network routes?  
    **A:** `traceroute` (Linux) or `tracert` (Windows).

---

### **5. Artifactory**
1. **Q:** What is Artifactory?  
   **A:** A universal artifact repository manager (supports Docker, npm, Maven, etc.).

2. **Q:** What is a "virtual repository"?  
   **A:** Aggregates multiple repositories (local/remote) under a single URL.

3. **Q:** How do you clean up old artifacts?  
   **A:** Use retention policies (e.g., delete snapshots older than 30 days).

4. **Q:** What is the difference between a snapshot and a release repo?  
   **A:** Snapshots are mutable (dev builds); releases are immutable (production).

5. **Q:** How to integrate Artifactory with Jenkins?  
   **A:** Use the Artifactory plugin to publish/resolve artifacts during builds.

6. **Q:** What is "replication" in Artifactory?  
   **A:** Syncs artifacts between instances (e.g., for disaster recovery).

7. **Q:** How do you secure access to Artifactory?  
   **A:** Use RBAC, SSO (SAML/OAuth), and encrypt sensitive data.

8. **Q:** What is the JFrog CLI?  
   **A:** Command-line tool to interact with Artifactory (upload/download artifacts).

9. **Q:** How do you resolve dependencies from Artifactory in Maven?  
   **A:** Configure `settings.xml` with Artifactory repo URLs.

10. **Q:** What is "Artifactory Edge Node"?  
    **A:** Local cache in CDN-like setups to reduce latency for distributed teams.

11. **Q:** How do you backup Artifactory?  
    **A:** Use the Export API or filesystem backups (include metadata and storage).

12. **Q:** What is a "Docker registry" in Artifactory?  
    **A:** A repository to store Docker images (supports push/pull).

13. **Q:** How to troubleshoot a failed artifact upload?  
    **A:** Check permissions, storage quota, and network connectivity.

14. **Q:** What is Xray in JFrog?  
    **A:** Security tool for scanning artifacts for vulnerabilities/licenses.

15. **Q:** How to set up a Maven repository in Artifactory?  
    **A:** Create a local/remote/virtual repo and configure Maven clients.

16. **Q:** What is "federated repositories"?  
    **A:** Replicates repositories across multiple Artifactory instances globally.

17. **Q:** How to restrict access to a specific repository?  
    **A:** Use permission targets and groups in Artifactory’s admin panel.

18. **Q:** What is the purpose of the `artifactory-cleanup` tool?  
    **A:** Deletes old/unused artifacts based on custom rules.

19. **Q:** How to migrate artifacts from Nexus to Artifactory?  
    **A:** Use the JFrog CLI or Import API.

20. **Q:** What is "Artifactory Query Language" (AQL)?  
    **A:** A syntax to search artifacts using criteria (e.g., date, properties).

---

### **6. Windows Server Admin**
1. **Q:** What is Active Directory (AD)?  
   **A:** Microsoft directory service for managing users, computers, and policies.

2. **Q:** How to promote a server to a Domain Controller?  
   **A:** Run `Install-ADDSForest` in PowerShell or use Server Manager.

3. **Q:** What is Group Policy?  
   **A:** Centralized settings management for users/computers in a domain.

4. **Q:** How to check if a service is running via PowerShell?  
   **A:** `Get-Service -Name <service-name>`.

5. **Q:** What is DNS and its role in AD?  
   **A:** Translates domain names to IPs; critical for locating domain controllers.

6. **Q:** How to reset a user’s password in AD?  
   **A:** Use `Set-ADAccountPassword` in PowerShell or AD Users and Computers.

7. **Q:** What is DHCP?  
   **A:** Assigns IP addresses dynamically to network devices.

8. **Q:** How to export a list of installed software on a server?  
   **A:** `Get-ItemProperty HKLM:\Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\* | Select-Object DisplayName`.

9. **Q:** What is the purpose of `gpupdate /force`?  
    **A:** Applies Group Policy updates immediately.

10. **Q:** How to check disk health in Windows Server?  
    **A:** Use `chkdsk` or PowerShell’s `Get-PhysicalDisk`.

11. **Q:** What is WSUS?  
    **A:** Windows Server Update Services—manages patches for Microsoft products.

12. **Q:** How to configure a static IP in Windows Server?  
    **A:** `Netsh` or via Network Connections GUI.

13. **Q:** What is a "Failover Cluster"?  
    **A:** Group of servers providing high availability for services/apps.

14. **Q:** How to enable Remote Desktop access?  
    **A:** Via System Properties > Remote tab or `Set-ItemProperty -Path 'HKLM:\System\CurrentControlSet\Control\Terminal Server' -Name fDenyTSConnections -Value 0`.

15. **Q:** What is NTFS permission inheritance?  
    **A:** Child objects (files/folders) inherit permissions from parent by default.

16. **Q:** How to monitor performance in Windows Server?  
    **A:** Use Performance Monitor (`perfmon`) or Resource Monitor.

17. **Q:** What is PowerShell Remoting?  
    **A:** Executes commands on remote servers via `Enter-PSSession` or `Invoke-Command`.

18. **Q:** How to backup a Windows Server?  
    **A:** Use Windows Server Backup (`wbadmin`) or third-party tools.

19. **Q:** What is Hyper-V?  
    **A:** Microsoft’s hypervisor for creating

---

### **7. Containerization-Docker**  
**Q1:** What is the difference between a Docker image and a container?  
**A1:** An image is a read-only template with instructions to create a container. A container is a running instance of an image.  

**Q2:** What command is used to build a Docker image from a Dockerfile?  
**A2:** `docker build -t <image-name> .`  

**Q3:** How do you persist data generated by a Docker container?  
**A3:** Use Docker volumes or bind mounts (e.g., `docker run -v /host/path:/container/path`).  

**Q4:** What is the purpose of `docker-compose`?  
**A4:** To define and run multi-container Docker applications using a YAML configuration file.  

**Q5:** Explain Docker’s default network driver.  
**A5:** The `bridge` network driver creates a private internal network for containers to communicate.  

**Q6:** How do you remove stopped containers and unused images?  
**A6:** `docker system prune` or `docker container prune` and `docker image prune`.  

**Q7:** What is the significance of `EXPOSE` in a Dockerfile?  
**A7:** It documents the port the container listens on but does not publish it. Use `-p` in `docker run` to publish.  

**Q8:** What is the difference between `CMD` and `ENTRYPOINT` in a Dockerfile?  
**A8:** `CMD` sets default commands/arguments, which can be overridden. `ENTRYPOINT` configures the executable.  

**Q9:** How do you run a Docker container in detached mode?  
**A9:** `docker run -d <image-name>`.  

**Q10:** What is the purpose of Docker Hub?  
**A10:** A cloud registry to store and share Docker images.  

**Q11:** What Linux kernel features does Docker use?  
**A11:** Namespaces (isolation) and cgroups (resource limits).  

**Q12:** How do you view logs of a running container?  
**A12:** `docker logs <container-id>`.  

**Q13:** What is a Dockerfile `COPY` instruction used for?  
**A13:** To copy files/directories from the host to the container filesystem.  

**Q14:** How do you list all running containers?  
**A14:** `docker ps` or `docker container ls`.  

**Q15:** What is the purpose of `docker exec`?  
**A15:** To execute a command inside a running container (e.g., `docker exec -it <container-id> bash`).  

**Q16:** How does Docker differ from a virtual machine (VM)?  
**A16:** Docker shares the host OS kernel, while VMs require a hypervisor and full OS.  

**Q17:** What is a multi-stage build in Docker?  
**A17:** A technique to reduce image size by using multiple `FROM` statements to separate build and runtime stages.  

**Q18:** How do you set environment variables in a container?  
**A18:** Use `-e` in `docker run` (e.g., `docker run -e VAR=value`) or `ENV` in the Dockerfile.  

**Q19:** What is Docker Swarm?  
**A19:** Docker’s native orchestration tool for managing clusters of containers.  

**Q20:** How do you push an image to Docker Hub?  
**A20:** `docker push <username>/<image-name>:<tag>`.  

---

### **8. Chef and Puppet**  
**Q1:** What is the primary difference between Chef and Puppet?  
**A1:** Chef uses Ruby for its DSL and follows an imperative approach, while Puppet uses a declarative DSL.  

**Q2:** What is a *recipe* in Chef?  
**A2:** A collection of resources (e.g., packages, files) defined in Ruby to configure a system.  

**Q3:** What is a *manifest* in Puppet?  
**A3:** A file (`.pp`) declaring resources (e.g., packages, services) to configure nodes.  

**Q4:** What is *idempotency* in configuration management?  
**A4:** Applying the same configuration repeatedly produces the same result without side effects.  

**Q5:** What is the Chef Server’s role?  
**A5:** Stores cookbooks, policies, and node metadata, and manages communication with nodes.  

**Q6:** How does Puppet enforce configurations?  
**A6:** Agents on nodes periodically pull configurations from the Puppet Master.  

**Q7:** What is a *cookbook* in Chef?  
**A7:** A reusable package containing recipes, templates, and files for configuring a service.  

**Q8:** What is *Facter* in Puppet?  
**A8:** A tool to collect system facts (e.g., OS, IP) used in Puppet manifests.  

**Q9:** How do you test Chef cookbooks locally?  
**A9:** Use tools like Test Kitchen with Vagrant or Docker.  

**Q10:** What is *Ohai* in Chef?  
**A10:** Collects system data (attributes) used in Chef recipes.  

**Q11:** How does Puppet handle dependencies between resources?  
**A11:** Using `require`, `before`, `notify`, and `subscribe` metaparameters.  

**Q12:** What is a *resource* in Chef/Puppet?  
**A12:** A declaration of a system component (e.g., a package, file, or service).  

**Q13:** What is the Chef *run-list*?  
**A13:** An ordered list of roles/recipes to apply to a node.  

**Q14:** What is *Hiera* in Puppet?  
**A14:** A key-value lookup tool for separating data from code in manifests.  

**Q15:** How do Chef and Puppet ensure security?  
**A15:** Both use SSL for client-server communication and encrypted data bags (Chef) or Hiera-eyaml (Puppet).  

**Q16:** What is a *role* in Chef?  
**A16:** A way to group recipes and attributes for nodes with similar functions.  

**Q17:** How does Puppet classify nodes?  
**A17:** Using node definitions in manifests or an External Node Classifier (ENC).  

**Q18:** What is the Chef *client*?  
**A18:** An agent that runs on nodes to apply configurations from the Chef Server.  

**Q19:** What is the Puppet Forge?  
**A19:** A repository for pre-built Puppet modules.  

**Q20:** Name a key advantage of Chef over Puppet.  
**A20:** Flexibility due to Ruby’s imperative DSL, which allows complex logic.  

---

### **9. Chaos Monkey**  
**Q1:** What is Chaos Monkey?  
**A1:** A Netflix tool that randomly terminates production instances to test system resilience.  

**Q2:** What is the goal of Chaos Engineering?  
**A2:** To identify weaknesses in systems by simulating failures.  

**Q3:** What prerequisites are needed before using Chaos Monkey?  
**A3:** Redundancy, monitoring, and automated recovery mechanisms.  

**Q4:** How does Chaos Monkey differ from traditional testing?  
**A4:** It tests systems in production, not just staging/development environments.  

**Q5:** What is a *blast radius* in chaos experiments?  
**A5:** The scope of impact (e.g., how many users/systems are affected).  

**Q6:** Name a tool similar to Chaos Monkey.  
**A6:** Gremlin, Chaos Toolkit, or AWS Fault Injection Simulator.  

**Q7:** What is the *Simian Army*?  
**A7:** A suite of Netflix tools (including Chaos Monkey) for testing cloud resilience.  

**Q8:** How does Chaos Monkey improve system reliability?  
**A8:** By forcing teams to design fault-tolerant systems.  

**Q9:** What types of failures does Chaos Monkey simulate?  
**A9:** Instance termination, network latency, or disk failures.  

**Q10:** What is a *GameDay*?  
**A10:** A planned chaos engineering exercise to test system resilience.  

**Q11:** Can Chaos Monkey be used in on-premises environments?  
**A11:** Yes, if configured to work with the infrastructure.  

**Q12:** What is the role of monitoring in chaos experiments?  
**A12:** To detect and measure the impact of failures.  

**Q13:** What is *mean time to recovery (MTTR)*?  
**A13:** The average time taken to recover from a failure.  

**Q14:** How do you limit Chaos Monkey’s impact?  
**A14:** Configure it to run only during business hours or exclude critical systems.  

**Q15:** What is the *Chaos Engineering Principle*?  
**A15:** “Inject failures proactively to build confidence in system resilience.”  

**Q16:** What is *latency injection*?  
**A16:** Introducing artificial network delays to test performance under stress.  

**Q17:** Why is automation critical for chaos experiments?  
**A17:** To ensure rapid recovery and repeatable tests.  

**Q18:** What is a *steady-state hypothesis* in chaos experiments?  
**A18:** A measurable condition that defines normal system behavior.  

**Q19:** Name a cloud provider integrated with Chaos Monkey.  
**A19:** AWS (via the Simian Army).  

**Q20:** How does Chaos Monkey help with compliance?  
**A20:** By validating disaster recovery (DR) and business continuity plans.  

---

### **10. Gradle**  
1. **Q:** What is the default build file in Gradle?  
   **A:** `build.gradle` or `build.gradle.kts` (for Kotlin).  

2. **Q:** How do you define a task in Gradle?  
   **A:**  
   ```groovy
   task myTask {
       doLast {
           println "Hello, Gradle!"
       }
   }
   ```

3. **Q:** What is the Gradle wrapper?  
   **A:** A script that ensures the correct Gradle version is used without manual installation.  

4. **Q:** How do you exclude a dependency in Gradle?  
   **A:**  
   ```groovy
   implementation('group:name') {
       exclude group: 'unwantedGroup', module: 'unwantedModule'
   }
   ```

5. **Q:** What is the command to list all tasks in a project?  
   **A:** `gradle tasks`  

6. **Q:** Explain the difference between `implementation` and `api` in dependency configurations.  
   **A:** `api` exposes dependencies to consumers, while `implementation` hides them.  

7. **Q:** What is a Gradle plugin?  
   **A:** Reusable logic to add features (e.g., Java, Spring Boot support).  

8. **Q:** How do you run a specific task?  
   **A:** `gradle :taskName`  

9. **Q:** What is the purpose of `settings.gradle`?  
   **A:** Configures project hierarchy (e.g., subprojects).  

10. **Q:** What is incremental build in Gradle?  
    **A:** Skips tasks if inputs/outputs haven’t changed, improving performance.  

11. **Q:** How do you force Gradle to re-download dependencies?  
    **A:** Delete the cache in `~/.gradle/caches/` or run `gradle build --refresh-dependencies`.  

12. **Q:** What is `gradle.properties` used for?  
    **A:** Configures project-wide settings (e.g., JVM args, version).  

13. **Q:** How do you create a multi-project build?  
    **A:** Define subprojects in `settings.gradle` using `include 'subprojectName'`.  

14. **Q:** What is the difference between `buildscript` and `allprojects` blocks?  
    **A:** `buildscript` defines dependencies for the build script itself; `allprojects` applies config to all subprojects.  

15. **Q:** How do you publish artifacts to a Maven repository?  
    **A:** Use the `maven-publish` plugin and configure `publishing.repositories`.  

16. **Q:** What is the purpose of `gradle init`?  
    **A:** Generates a new project structure.  

17. **Q:** How do you enable the Kotlin DSL in Gradle?  
    **A:** Use `build.gradle.kts` instead of `build.gradle`.  

18. **Q:** What is a `BuildListener` in Gradle?  
    **A:** A callback to react to build lifecycle events (e.g., task execution).  

19. **Q:** How do you configure a project to use a specific Java version?  
    **A:**  
    ```groovy
    java {
        toolchain {
            languageVersion = JavaLanguageVersion.of(17)
        }
    }
    ```

20. **Q:** What is the difference between `gradle assemble` and `gradle build`?  
    **A:** `assemble` compiles code and packages artifacts; `build` also runs tests.  

---

### **11. Maven**  
1. **Q:** What is the default build file in Maven?  
   **A:** `pom.xml`.  

2. **Q:** What are the three main phases of the Maven lifecycle?  
   **A:** `clean`, `default` (build), `site`.  

3. **Q:** What is the command to create a new project?  
   **A:** `mvn archetype:generate`.  

4. **Q:** How do you exclude a dependency?  
   **A:**  
   ```xml
   <exclusions>
       <exclusion>
           <groupId>...</groupId>
           <artifactId>...</artifactId>
       </exclusion>
   </exclusions>
   ```

5. **Q:** What is the difference between `SNAPSHOT` and release versions?  
   **A:** `SNAPSHOT` denotes a work-in-progress; releases are stable.  

6. **Q:** What is the purpose of `mvn install`?  
   **A:** Builds the project and installs the artifact to the local repository.  

7. **Q:** Explain dependency scopes: `compile`, `test`, `provided`.  
   **A:**  
   - `compile`: Available in all classpaths.  
   - `test`: Only for testing.  
   - `provided`: Provided by the runtime (e.g., Servlet API).  

8. **Q:** What is a Maven plugin?  
   **A:** Extends Maven’s functionality (e.g., `maven-surefire-plugin` for tests).  

9. **Q:** What is the default packaging type?  
   **A:** `jar`.  

10. **Q:** How do you skip tests during a build?  
    **A:** `mvn install -DskipTests`.  

11. **Q:** What is the purpose of the `dependencyManagement` section?  
    **A:** Centralizes dependency versions for child modules.  

12. **Q:** What is a transitive dependency?  
    **A:** Dependencies of your dependencies, automatically included.  

13. **Q:** How do you resolve a dependency conflict?  
    **A:** Use `<dependencyManagement>` or explicitly exclude conflicting versions.  

14. **Q:** What is the `settings.xml` file?  
    **A:** Configures global or user-specific Maven settings (e.g., repositories, proxies).  

15. **Q:** What is the difference between `mvn package` and `mvn deploy`?  
    **A:** `package` creates the artifact; `deploy` uploads it to a remote repository.  

16. **Q:** How do you add a remote repository?  
    **A:** Define it in `pom.xml` under `<repositories>`.  

17. **Q:** What is a Maven profile?  
    **A:** A set of configurations activated based on conditions (e.g., environment).  

18. **Q:** What is the `effective POM`?  
    **A:** The final POM after merging parent and child configurations.  

19. **Q:** How do you list all dependencies in a project?  
    **A:** `mvn dependency:tree`.  

20. **Q:** What is the purpose of the `mvn clean` command?  
    **A:** Deletes the `target` directory.  

---

### **12. GIT**  
1. **Q:** What is the command to initialize a Git repository?  
   **A:** `git init`.  

2. **Q:** How do you stage all changes for commit?  
   **A:** `git add .`  

3. **Q:** What is the difference between `git fetch` and `git pull`?  
   **A:** `fetch` retrieves changes but doesn’t merge; `pull` does `fetch` + `merge`.  

4. **Q:** How do you create and switch to a new branch?  
   **A:** `git checkout -b branchName`.  

5. **Q:** What is a merge conflict, and how do you resolve it?  
   **A:** Occurs when changes conflict; resolve by editing files, then `git add` and `git commit`.  

6. **Q:** What is `git rebase`?  
   **A:** Rewrites commit history by moving branches to a new base commit.  

7. **Q:** How do you undo the last commit?  
   **A:** `git reset HEAD~1` (soft reset) or `git reset --hard HEAD~1` (discard changes).  

8. **Q:** What is the purpose of `.gitignore`?  
   **A:** Specifies files/directories to exclude from version control.  

9. **Q:** How do you view the commit history?  
   **A:** `git log`.  

10. **Q:** What is a detached HEAD state?  
    **A:** When you check out a commit directly instead of a branch.  

11. **Q:** How do you delete a remote branch?  
    **A:** `git push origin --delete branchName`.  

12. **Q:** What is `git stash`?  
    **A:** Temporarily saves uncommitted changes.  

13. **Q:** How do you revert a specific commit?  
    **A:** `git revert commitHash`.  

14. **Q:** What is the difference between `git reset` and `git revert`?  
    **A:** `reset` moves the HEAD pointer; `revert` creates a new commit undoing changes.  

15. **Q:** What is a `fast-forward` merge?  
    **A:** Merging by moving a branch pointer forward without creating a merge commit.  

16. **Q:** How do you tag a commit?  
    **A:** `git tag -a v1.0 -m "Message" commitHash`.  

17. **Q:** What is `git cherry-pick`?  
    **A:** Applies a specific commit from one branch to another.  

18. **Q:** How do you configure Git to use a proxy?  
    **A:**  
    ```bash
    git config --global http.proxy http://proxy.example.com:8080
    ```

19. **Q:** What is `git bisect`?  
    **A:** Helps find the commit that introduced a bug via binary search.  

20. **Q:** How do you clone a remote repository?  
    **A:** `git clone https://github.com/user/repo.git`.  

---

### **13. Ansible**  
1. **Q:** What is an Ansible playbook?  
   **A:** A YAML file defining automation tasks.  

2. **Q:** How do you run a playbook?  
   **A:** `ansible-playbook playbook.yml`.  

3. **Q:** What is an inventory file?  
   **A:** Lists managed hosts/groups (e.g., `/etc/ansible/hosts`).  

4. **Q:** What is the difference between `ansible` and `ansible-playbook`?  
   **A:** `ansible` runs ad-hoc commands; `ansible-playbook` executes playbooks.  

5. **Q:** How do you define variables in a playbook?  
   **A:**  
   ```yaml
   vars:
     my_var: "value"
   ```

6. **Q:** What is an Ansible role?  
   **A:** Reusable collection of tasks, variables, and handlers.  

7. **Q:** What is idempotency in Ansible?  
   **A:** Running a task multiple times has the same effect as running it once.  

8. **Q:** How do you handle secrets in Ansible?  
   **A:** Use `ansible-vault` to encrypt files.  

9. **Q:** What is a handler?  
   **A:** A task triggered by `notify` (e.g., restarting a service).  

10. **Q:** What is the `become` keyword?  
    **A:** Escalates privileges (e.g., `sudo`).  

11. **Q:** How do you test a playbook without executing it?  
    **A:** `ansible-playbook --check playbook.yml`.  

12. **Q:** What is the purpose of the `gather_facts` task?  
    **A:** Collects system information (e.g., OS, IP).  

13. **Q:** How do you loop over items in a task?  
    **A:**  
    ```yaml
    loop:
      - item1
      - item2
    ```

14. **Q:** What is the `ansible.cfg` file?  
    **A:** Configures Ansible settings (e.g., inventory path).  

15. **Q:** What is the difference between `shell` and `command` modules?  
    **A:** `shell` runs commands in a shell (supports pipes/variables); `command` runs directly.  

16. **Q:** How do you create a dynamic inventory?  
    **A:** Use scripts that output JSON (e.g., AWS EC2 inventory script).  

17. **Q:** What is a Jinja2 template in Ansible?  
    **A:** A file with variables populated by Ansible (e.g., `template` module).  

18. **Q:** How do you conditionally run a task?  
    **A:** Use `when`:  
    ```yaml
    when: ansible_os_family == "Debian"
    ```

19. **Q:** What is the `debug` module used for?  
    **A:** Prints variables or messages during execution.  

20. **Q:** How do you install a package using Ansible?  
    **A:** Use the `apt` (Debian) or `yum` (RHEL) module:  
    ```yaml
    - name: Install nginx
      apt:
        name: nginx
        state: present
    ```

---

### **14. Jenkins**  
1. **Q:** What is a Jenkins pipeline?  
   **A:** A scripted or declarative workflow for CI/CD.  

2. **Q:** How do you define a Declarative Pipeline?  
   **A:** Using a `Jenkinsfile` with `pipeline`, `agent`, and `stages` blocks.  

3. **Q:** What is the purpose of the `agent` directive?  
   **A:** Specifies where the pipeline runs (e.g., `any`, `docker`).  

4. **Q:** What is a Jenkinsfile?  
   **A:** A text file storing the pipeline configuration.  

5. **Q:** How do you trigger a Jenkins job on Git commit?  
   **A:** Use webhooks or SCM polling.  

6. **Q:** What is a Jenkins workspace?  
   **A:** The directory where the project is checked out and built.  

7. **Q:** How do you parameterize a Jenkins job?  
   **A:** Use the `Parameters` section (e.g., string, choice parameters).  

8. **Q:** What is Blue Ocean in Jenkins?  
   **A:** A modern UI for visualizing pipelines.  

9. **Q:** How do you handle secrets in Jenkins?  
   **A:** Use the "Credentials" store (e.g., username/password, SSH keys).  

10. **Q:** What is the difference between Scripted and Declarative Pipelines?  
    **A:** Declarative uses a structured syntax; Scripted uses Groovy for flexibility.  

11. **Q:** How do you run a parallel stage?  
    **A:**  
    ```groovy
    stages {
        stage('Parallel') {
            parallel {
                stage('Test1') { ... }
                stage('Test2') { ... }
            }
        }
    }
    ```

12. **Q:** What is the purpose of the `post` block?  
    **A:** Defines actions after stages (e.g., cleanup, notifications).  

13. **Q:** How do you archive artifacts in Jenkins?  
    **A:** Use the `archiveArtifacts` step:  
    ```groovy
    archiveArtifacts artifacts: '**/target/*.jar'
    ```

14. **Q:** What is a Jenkins shared library?  
    **A:** Reusable Groovy code stored in a repository for pipelines.  

15. **Q:** How do you restart Jenkins?  
    **A:** Use `/safeRestart` via the web UI or touch the `restart` file in `JENKINS_HOME`.  

16. **Q:** What is the purpose of the `Jenkinsfile` `environment` block?  
    **A:** Defines environment variables for the pipeline.  

17. **Q:** How do you integrate Jenkins with GitHub?  
    **A:** Use the GitHub plugin and webhooks.  

18. **Q:** What is a Jenkins agent?  
    **A:** A machine/node that executes pipeline tasks.  

19. **Q:** How do you handle pipeline failures?  
    **A:** Use `post { failure { ... } }` or `catchError` in Scripted Pipelines.  

20. **Q:** What is the purpose of the `input` step?  
    **A:** Pauses the pipeline for user approval (e.g., production deployment).  

---
