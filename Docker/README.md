# Docker Interview Preparation – Casebook Style 🐳

This document is curated from **real Docker interview questions and scenario-based discussions**
commonly shared by **DevOps engineers on LinkedIn and real interviews**.

Each question includes:
- 📌 Clear Answer
- 🧠 Why it matters in real systems
- ⚠️ Common pitfalls
- 🛠️ Real-world troubleshooting or usage

---

## 1. What is Docker and why is it used?

📌 **Answer:**  
Docker is a containerization platform that allows applications to be packaged along with their dependencies into a single unit called a container.

🧠 **Why it matters:**  
Containers ensure consistency across environments (dev, QA, prod) and enable faster deployments.

⚠️ **Common Pitfall:**  
Confusing containers with virtual machines. Containers share the host OS kernel.

🛠️ **Real-world usage:**  
Used heavily in CI/CD pipelines to ensure repeatable builds.

---

## 2. What is the difference between Docker Image and Docker Container?

📌 **Answer:**  
- Image → Read-only blueprint
- Container → Running instance of an image

🧠 **Why it matters:**  
Understanding this distinction is crucial for debugging runtime issues.

⚠️ **Pitfall:**  
Trying to persist data inside containers instead of using volumes.

---

## 3. What happens when you run `docker run`?

📌 **Answer:**  
Docker performs:
1. Pulls image (if not present)
2. Creates a container
3. Allocates network
4. Starts the container

🧠 **Why it matters:**  
Explains container lifecycle clearly in interviews.

---

## 4. How is Docker different from Virtual Machines?

📌 **Answer:**  
Docker containers share the host kernel, whereas VMs include a full OS.

🧠 **Why it matters:**  
Explains why containers are lightweight and fast.

---

## 5. What is a Dockerfile?

📌 **Answer:**  
A Dockerfile is a script containing instructions to build a Docker image.

🛠️ **Common Instructions:**
- FROM
- RUN
- COPY
- CMD
- ENTRYPOINT

⚠️ **Pitfall:**  
Too many layers due to multiple RUN commands.

---

## 6. Explain CMD vs ENTRYPOINT

📌 **Answer:**  
- CMD → Default arguments
- ENTRYPOINT → Fixed executable

🧠 **Why it matters:**  
Important when building production-ready images.

---

## 7. How do you reduce Docker image size?

📌 **Answer:**  
- Use slim or alpine images
- Multi-stage builds
- Clean package cache

🛠️ **Example:**  
Using `FROM node:alpine` instead of `node:latest`.

---

## 8. What are Docker volumes and why are they needed?

📌 **Answer:**  
Volumes provide persistent storage outside containers.

🧠 **Why it matters:**  
Containers are ephemeral by design.

⚠️ **Pitfall:**  
Storing database data inside container filesystem.

---

## 9. A container keeps restarting. How do you debug?

📌 **Answer:**  
1. Check status:
```bash
docker ps -a
```
2. Inspect logs:
```bash
docker logs <container-id>
```
3. Inspect container:
```bash
docker inspect <container-id>
```

🧠 **Why it matters:**  
Very common real-world interview scenario.

---

## 10. What is Docker networking?

📌 **Answer:**  
Docker provides bridge, host, overlay, and none networks.

🛠️ **Most Common:**  
Bridge network for single-host deployments.

---

## 11. Difference between COPY and ADD

📌 **Answer:**  
- COPY → Simple file copy
- ADD → Supports URL & tar extraction

⚠️ **Best Practice:**  
Prefer COPY unless ADD features are required.

---

## 12. How do containers communicate with each other?

📌 **Answer:**  
Via Docker networks using container names as DNS.

🧠 **Prevent hardcoding IPs** in interviews.

---

## 13. Docker container exits immediately. Why?

📌 **Answer:**  
Main process finished or crashed.

🛠️ **Fix:**  
Run container in foreground or keep process alive.

---

## 14. What is Docker Compose?

📌 **Answer:**  
Tool to define and run multi-container applications using `docker-compose.yml`.

🧠 **Why it matters:**  
Used heavily for local development and testing.

---

## 15. Docker build is slow. How do you optimize?

📌 **Answer:**  
- Use build cache efficiently
- Order Dockerfile instructions properly
- Avoid copying unnecessary files

---

## 16. Difference between EXPOSE and -p

📌 **Answer:**  
- EXPOSE → Documentation
- -p → Actual port mapping

---

## 17. How do you secure Docker?

📌 **Answer:**  
- Use minimal base images
- Scan images for vulnerabilities
- Avoid running as root
- Use trusted registries

---

## 18. What is a dangling image?

📌 **Answer:**  
Unused image layers without tags.

🛠️ **Cleanup:**
```bash
docker image prune
```

---

## 19. Docker container cannot connect to internet. What do you check?

📌 **Answer:**  
- Network settings
- DNS resolution
- Firewall rules

---

## 20. Docker vs Podman (Interview Bonus)

📌 **Answer:**  
Podman is daemonless and rootless by design.

🧠 **Why it matters:**  
Shows awareness of modern container tools.

---

📌 **Final Interview Tip:**  
Always explain Docker answers in terms of **portability, consistency, and automation**.
