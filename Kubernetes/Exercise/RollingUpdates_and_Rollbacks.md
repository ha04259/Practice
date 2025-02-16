https://uklabs.kodekloud.com/topic/labs-practice-te…es-and-rollbacks/

### Deployment Strategies for VM-Based Environments (e.g., AWS EC2)

1. **In-Place Deployment**  
   - **Description**: Update existing EC2 instances directly (e.g., via SSH).  
   - **Pros**: Simple, no additional infrastructure costs.  
   - **Cons**: Downtime risk, no easy rollback.  

2. **Blue-Green Deployment**  
   - **Description**:  
     - **Blue**: Current production environment.  
     - **Green**: New version deployed alongside.  
     - Traffic is switched (via load balancer or DNS) after validation.  
   - **Pros**: Minimal downtime, easy rollback.  
   - **Cons**: Requires double resources during transition.  

3. **Rolling Deployment**  
   - **Description**: Incrementally replace old instances with new ones (e.g., using Auto Scaling Groups).  
   - **Pros**: No downtime, gradual rollout.  
   - **Cons**: Complex to manage stateful workloads.  

4. **Canary Deployment**  
   - **Description**: Route a small % of traffic to new instances. Gradually increase if stable.  
   - **Pros**: Low-risk testing in production.  
   - **Cons**: Requires advanced traffic routing (e.g., ALB, NGINX).  

5. **Immutable Deployment**  
   - **Description**: Replace old instances with new ones (no in-place updates).  
     - Use AMIs or launch templates for consistency.  
   - **Pros**: Consistency, reduced configuration drift.  
   - **Cons**: Longer deployment time.  

6. **Phased Deployment**  
   - **Description**: Deploy in stages (e.g., dev → staging → production).  
   - **Pros**: Controlled risk.  
   - **Cons**: Slower delivery.  

7. **Traffic Shifting**  
   - **Description**: Use weighted DNS (Route 53) or load balancers to shift traffic.  
   - **Tools**: AWS Elastic Load Balancer (ELB), HAProxy.  

---

### Deployment Strategies for Kubernetes

1. **Rolling Update (Default)**  
   - **Description**: Gradually replace old pods with new ones.  
     - Controlled by `Deployment` object (`maxSurge`, `maxUnavailable`).  
   - **Pros**: Zero downtime, automated.  
   - **Cons**: No version testing in production.  

2. **Recreate Strategy**  
   - **Description**: Terminate all old pods before creating new ones.  
   - **Pros**: Simplicity.  
   - **Cons**: Downtime during replacement.  

3. **Blue-Green Deployment**  
   - **Description**:  
     - **Blue**: Current deployment.  
     - **Green**: New deployment.  
     - Switch traffic by updating the `Service` selector.  
   - **Pros**: Instant rollback, no overlap.  
   - **Cons**: Resource-intensive.  

4. **Canary Deployment**  
   - **Description**:  
     - Deploy a small subset of new pods.  
     - Use `Service` mesh (e.g., Istio) or ingress controllers (e.g., Nginx) to split traffic.  
   - **Pros**: Test in production safely.  
   - **Cons**: Complex setup.  

5. **A/B Testing**  
   - **Description**: Route traffic based on user attributes (e.g., headers, cookies).  
   - **Tools**: Istio, Flagger.  
   - **Use Case**: Feature validation with specific user segments.  

6. **Shadow (Mirroring)**  
   - **Description**: Mirror live traffic to a new version without impacting users.  
   - **Pros**: Test performance/errors without risk.  
   - **Cons**: High resource usage.  

7. **Database Migration Strategies**  
   - **Description**: Use sidecar containers or init containers for schema updates.  
   - **Tools**: Liquibase, Flyway.  

8. **Feature Flags**  
   - **Description**: Toggle features dynamically using tools like LaunchDarkly.  
   - **Pros**: Decouple deployment from release.  

---

### Key Tools for Each Platform  
- **VM/EC2**: AWS CodeDeploy, Terraform, Ansible, Packer (AMIs).  
- **Kubernetes**: Argo Rollouts, Flagger, Istio, Helm (for templating).  

Let me know if you need implementation examples for any strategy! 🚀
