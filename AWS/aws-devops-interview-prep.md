# AWS for DevOps Interview Preparation – Casebook Style ☁️

This document is curated for **DevOps interviews**, focusing on **real AWS questions and production scenarios**
commonly discussed by DevOps engineers.

Each question includes:
- 📌 Clear explanation
- 🧠 Why it matters in production
- ⚠️ Common mistakes
- 🛠️ Real-world troubleshooting or usage

---

## 1. Why is AWS widely used in DevOps?

📌 **Answer:**  
AWS provides scalable, reliable, and on-demand cloud infrastructure that integrates well with automation and CI/CD pipelines.

🧠 **Why it matters:**  
DevOps relies on elasticity, automation, and pay-as-you-go infrastructure.

⚠️ **Mistake:**  
Treating AWS like traditional on-prem servers.

---

## 2. Explain EC2 and its use cases.

📌 **Answer:**  
Amazon EC2 provides resizable virtual machines in the cloud.

🧠 **Why it matters:**  
EC2 is commonly used for application servers, Jenkins, and custom workloads.

🛠️ **Interview scenario:**  
Choosing instance types based on CPU vs memory needs.

---

## 3. What is IAM and why is it critical?

📌 **Answer:**  
IAM controls authentication and authorization in AWS.

🧠 **Why it matters:**  
Security in AWS starts with IAM.

⚠️ **Mistake:**  
Using root user for daily operations.

---

## 4. Explain IAM Roles vs Users.

📌 **Answer:**  
- Users → Human access
- Roles → Service-to-service access

🧠 **Why it matters:**  
Roles enable secure, temporary credentials.

---

## 5. What is VPC?

📌 **Answer:**  
A VPC is an isolated virtual network in AWS.

🧠 **Why it matters:**  
Provides control over networking, routing, and security.

---

## 6. Public vs Private Subnet.

📌 **Answer:**  
- Public → Internet accessible
- Private → No direct internet access

🛠️ **Real use case:**  
App in private subnet, ALB in public subnet.

---

## 7. What are Security Groups and NACLs?

📌 **Answer:**  
- Security Groups → Stateful, instance-level
- NACLs → Stateless, subnet-level

---

## 8. How does Auto Scaling work?

📌 **Answer:**  
Automatically adjusts EC2 capacity based on metrics.

🧠 **Why it matters:**  
Ensures high availability and cost efficiency.

---

## 9. What is an ALB and when do you use it?

📌 **Answer:**  
Application Load Balancer routes HTTP/HTTPS traffic.

🛠️ **Use case:**  
Microservices and Kubernetes ingress.

---

## 10. What is S3 and common DevOps use cases?

📌 **Answer:**  
Object storage for backups, artifacts, and logs.

🧠 **Why it matters:**  
Durable and cost-effective storage.

---

## 11. Difference between S3 and EBS.

📌 **Answer:**  
- S3 → Object storage
- EBS → Block storage attached to EC2

---

## 12. What is CloudWatch?

📌 **Answer:**  
Monitoring and logging service for AWS resources.

🛠️ **Use case:**  
Alarms, metrics, log analysis.

---

## 13. Application is slow on AWS. How do you diagnose?

🛠️ **Steps:**
- Check EC2 metrics
- Review CloudWatch logs
- Check load balancer health checks

---

## 14. What is EKS and why is it used?

📌 **Answer:**  
EKS is AWS-managed Kubernetes service.

🧠 **Why it matters:**  
Reduces operational overhead of managing Kubernetes.

---

## 15. Difference between ECS and EKS.

📌 **Answer:**  
- ECS → AWS-native container orchestration
- EKS → Kubernetes-based

---

## 16. How do you secure AWS infrastructure?

📌 **Answer:**  
- IAM least privilege
- Security groups
- Encryption at rest and transit
- Regular audits

---

## 17. What is Infrastructure as Code in AWS?

📌 **Answer:**  
Managing infrastructure using code.

🛠️ **Tools:**  
CloudFormation, Terraform

---

## 18. AWS costs suddenly spike. What do you check?

📌 **Answer:**  
- Cost Explorer
- Unused resources
- Scaling misconfigurations

---

## 19. How do you design highly available systems in AWS?

📌 **Answer:**  
- Multi-AZ deployments
- Load balancers
- Auto Scaling

---

## 20. IAM permission denied error. How do you debug?

🛠️ **Steps:**
- Check attached policies
- Verify role assumption
- Review CloudTrail logs

---

📌 **Final Interview Tip:**  
Always explain AWS answers in terms of **security, scalability, and cost optimization**.
