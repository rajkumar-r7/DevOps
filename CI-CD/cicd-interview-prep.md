# CI/CD Interview Preparation – Jenkins & GitHub Actions 🚀

This document is curated for **DevOps interview preparation**, based on **real CI/CD interview questions**
and scenario-based discussions shared by DevOps engineers in production environments.

Each question includes:
- 📌 Clear Answer
- 🧠 Why it matters in real-world CI/CD
- ⚠️ Common mistakes
- 🛠️ Practical troubleshooting scenarios

---

## 1. What is CI/CD and why is it important?

📌 **Answer:**  
CI/CD stands for Continuous Integration and Continuous Delivery/Deployment.  
It automates code integration, testing, and deployment.

🧠 **Why it matters:**  
CI/CD reduces manual errors, speeds up releases, and ensures consistent deployments.

⚠️ **Mistake:**  
Thinking CI/CD is only about tools — it is primarily a **process and culture**.

---

## 2. What is Jenkins?

📌 **Answer:**  
Jenkins is an open-source automation server used to build CI/CD pipelines.

🧠 **Why it matters:**  
Jenkins is still widely used in enterprises and legacy systems.

---

## 3. What is GitHub Actions?

📌 **Answer:**  
GitHub Actions is a CI/CD platform integrated directly with GitHub repositories.

🧠 **Why it matters:**  
Reduces tool sprawl and simplifies pipeline management.

---

## 4. Jenkins vs GitHub Actions

📌 **Answer:**  
- Jenkins → Self-hosted, highly customizable
- GitHub Actions → Managed, GitHub-native

🧠 **Interview Tip:**  
Mention **when to choose which**.

---

## 5. What is a Jenkins Pipeline?

📌 **Answer:**  
A Jenkins Pipeline defines CI/CD workflows as code using a Jenkinsfile.

🛠️ **Types:**
- Declarative
- Scripted

---

## 6. What is a Jenkinsfile?

📌 **Answer:**  
A Jenkinsfile is a text file that defines pipeline stages and steps.

🧠 **Why it matters:**  
Pipeline-as-Code enables version control and auditability.

---

## 7. Explain Jenkins architecture.

📌 **Answer:**  
- Jenkins Controller
- Jenkins Agents (workers)

🧠 **Why it matters:**  
Helps diagnose build performance and scalability issues.

---

## 8. Build is stuck in Jenkins. What do you check?

🛠️ **Troubleshooting:**
- Agent availability
- Executor limits
- Console logs
- Disk space

---

## 9. What are Jenkins plugins?

📌 **Answer:**  
Plugins extend Jenkins functionality (Git, Docker, Slack, etc.).

⚠️ **Pitfall:**  
Too many plugins can cause instability.

---

## 10. How do you secure Jenkins?

📌 **Answer:**  
- Enable authentication & authorization
- Use role-based access control
- Secure secrets with credentials store
- Restrict script approvals

---

## 11. What is a GitHub Actions workflow?

📌 **Answer:**  
A workflow is a YAML file that defines CI/CD steps triggered by events.

🛠️ **Location:**  
`.github/workflows/*.yml`

---

## 12. What are runners in GitHub Actions?

📌 **Answer:**  
Runners execute jobs in workflows.

🧠 **Types:**
- GitHub-hosted
- Self-hosted

---

## 13. Pipeline fails only in CI but works locally. Why?

📌 **Answer:**  
- Environment differences
- Missing dependencies
- Permission issues
- Hardcoded paths

🧠 **Interview Insight:**  
Always mention reproducibility.

---

## 14. How do you handle secrets in CI/CD?

📌 **Answer:**  
- Jenkins Credentials Store
- GitHub Secrets

⚠️ **Never hardcode secrets** in pipelines.

---

## 15. What is artifact management in CI/CD?

📌 **Answer:**  
Artifacts are build outputs stored for later stages or deployments.

🛠️ **Examples:**  
JAR files, Docker images

---

## 16. Jenkins job fails intermittently. How do you debug?

📌 **Answer:**  
- Network issues
- Resource constraints
- External dependency failures

---

## 17. How do you implement Docker in CI/CD pipelines?

📌 **Answer:**  
- Build Docker images
- Run tests inside containers
- Push images to registry

🧠 **Why it matters:**  
Ensures consistent environments.

---

## 18. What is Blue-Green or Canary deployment?

📌 **Answer:**  
Deployment strategies to reduce downtime and risk.

🧠 **Used heavily with Kubernetes and CI/CD pipelines.**

---

## 19. GitHub Actions workflow is not triggering. What do you check?

📌 **Answer:**  
- Event triggers
- Branch names
- YAML syntax
- Repo permissions

---

## 20. How do you optimize CI/CD pipelines?

📌 **Answer:**  
- Parallel jobs
- Caching dependencies
- Reduce build steps
- Fail fast strategy

---

📌 **Final Interview Tip:**  
Always explain CI/CD in terms of **speed, reliability, and automation maturity**.
