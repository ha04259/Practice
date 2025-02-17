

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
