# Infrastructure as Code Interview Preparation  
## Terraform & AWS CloudFormation – Casebook Style 🌍☁️

This document is curated for **DevOps interviews**, combining **Terraform and AWS CloudFormation**
questions frequently asked in real interviews and discussed by practicing DevOps engineers.

Each section explains:
- 📌 Conceptual clarity
- 🧠 Why it matters in real production systems
- ⚠️ Common interview mistakes
- 🛠️ Real-world scenarios and troubleshooting

---

# PART 1: Infrastructure as Code (IaC) Fundamentals

## 1. What is Infrastructure as Code (IaC)?

📌 **Answer:**  
Infrastructure as Code is the practice of managing infrastructure using code instead of manual configuration through consoles or GUIs.

🧠 **Why it matters:**  
IaC enables:
- Repeatable deployments
- Version control
- Automation
- Disaster recovery

⚠️ **Common mistake:**  
Using IaC but still making manual changes in the cloud console, causing drift.

---

## 2. What are the benefits of IaC?

📌 **Answer:**  
- Consistency across environments
- Faster provisioning
- Easy rollback
- Auditability

🧠 **Interview insight:**  
IaC is foundational to DevOps and GitOps practices.

---

# PART 2: Terraform – Interview Casebook

## 3. What is Terraform?

📌 **Answer:**  
Terraform is an open-source Infrastructure as Code tool by HashiCorp that allows you to provision and manage infrastructure across multiple cloud providers.

🧠 **Why it matters:**  
Terraform is **cloud-agnostic**, making it suitable for multi-cloud and hybrid environments.

---

## 4. Terraform vs CloudFormation (High-Value Interview Question)

📌 **Answer:**  

| Terraform | CloudFormation |
|---------|---------------|
| Multi-cloud | AWS-only |
| Uses HCL | Uses JSON/YAML |
| External state file | AWS-managed state |
| Large community | AWS-native |

🧠 **Interview tip:**  
Explain **when** you would choose each tool.

---

## 5. What is a Terraform Provider?

📌 **Answer:**  
A provider is a plugin that enables Terraform to communicate with cloud APIs such as AWS, Azure, or GCP.

---

## 6. What is Terraform State and why is it important?

📌 **Answer:**  
Terraform state tracks the mapping between configuration and real infrastructure.

🧠 **Why it matters:**  
Without state, Terraform cannot determine what changes are required.

⚠️ **Critical mistake:**  
Storing state locally in a team environment.

---

## 7. How do you manage Terraform state in production?

📌 **Answer:**  
- Remote backend (S3 + DynamoDB for locking)
- Terraform Cloud

🛠️ **Scenario:**  
Multiple engineers running Terraform simultaneously.

---

## 8. What is Terraform drift?

📌 **Answer:**  
Drift occurs when infrastructure is modified outside Terraform.

🛠️ **Detection:**  
```bash
terraform plan
```

---

## 9. Terraform apply fails halfway. What do you do?

📌 **Answer:**  
- Review error logs
- Inspect state file
- Re-run plan
- Avoid manual deletions

---

# PART 3: AWS CloudFormation – Interview Casebook

## 10. What is AWS CloudFormation?

📌 **Answer:**  
AWS CloudFormation is an AWS-native Infrastructure as Code service used to provision AWS resources using templates.

🧠 **Why it matters:**  
Tightly integrated with AWS services and IAM.

---

## 11. What is a CloudFormation template?

📌 **Answer:**  
A YAML or JSON file describing AWS resources and their relationships.

🛠️ **Key sections:**
- Parameters
- Resources
- Outputs

---

## 12. How does CloudFormation handle state?

📌 **Answer:**  
AWS manages state automatically using **stacks**.

🧠 **Why it matters:**  
Less state management overhead compared to Terraform.

---

## 13. What is a CloudFormation Stack?

📌 **Answer:**  
A stack is a collection of AWS resources managed as a single unit.

---

## 14. CloudFormation stack update fails. What do you do?

📌 **Answer:**  
- Check stack events
- Review rollback status
- Fix template errors
- Re-deploy

---

## 15. How do you handle secrets in CloudFormation?

📌 **Answer:**  
- AWS Secrets Manager
- AWS Systems Manager Parameter Store

⚠️ **Mistake:**  
Hardcoding secrets in templates.

---

# PART 4: Terraform vs CloudFormation – Scenario-Based

## 16. Which tool would you choose and why?

📌 **Answer:**  
- Use **Terraform** for:
  - Multi-cloud environments
  - Complex modules
  - Strong community support

- Use **CloudFormation** for:
  - AWS-only environments
  - Deep AWS service integrations
  - Managed state simplicity

🧠 **Interview tip:**  
There is no “one correct tool” — context matters.

---

## 17. Infrastructure changed manually in AWS console. What happens?

📌 **Answer:**  
- Terraform → Drift detected during plan
- CloudFormation → Stack drift detection

---

## 18. How do you secure IaC pipelines?

📌 **Answer:**  
- Least privilege IAM roles
- Secure state storage
- Code reviews
- CI/CD integration

---

## 19. Terraform works locally but fails in CI. Why?

📌 **Answer:**  
- Missing IAM permissions
- Backend access issues
- Different Terraform versions

---

## 20. When should you avoid IaC tools?

📌 **Answer:**  
- One-time manual changes
- Temporary debugging tasks

🧠 **Final Interview Insight:**  
IaC tools are about **safety, consistency, and automation**, not speed alone.

---

📌 **Closing Tip:**  
Interviewers care more about **decision-making and trade-offs** than tool syntax.
