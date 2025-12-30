# Kubernetes Interview Preparation – Casebook Style ☸️

This document is designed for **DevOps & SRE interviews**, based on **real Kubernetes questions**
frequently discussed by engineers in interviews and professional forums.

Each question includes:
- 📌 Clear explanation
- 🧠 Why it matters in production
- ⚠️ Common mistakes
- 🛠️ Troubleshooting / real-world scenarios

---

## 1. What is Kubernetes and why is it needed?

📌 **Answer:**  
Kubernetes is a container orchestration platform used to deploy, scale, and manage containerized applications.

🧠 **Why it matters:**  
In production, running containers manually is not scalable. Kubernetes provides automation, self-healing, and high availability.

⚠️ **Common mistake:**  
Thinking Kubernetes replaces Docker — Kubernetes orchestrates containers, it does not build them.

---

## 2. Explain Kubernetes architecture.

📌 **Answer:**  
Kubernetes consists of:
- Control Plane (API Server, Scheduler, Controller Manager, etcd)
- Worker Nodes (kubelet, kube-proxy, container runtime)

🧠 **Why it matters:**  
Understanding architecture helps debug cluster-level issues.

---

## 3. What is a Pod?

📌 **Answer:**  
A Pod is the smallest deployable unit in Kubernetes and can contain one or more containers sharing the same network and storage.

⚠️ **Mistake:**  
Deploying applications directly as pods instead of using Deployments.

---

## 4. What is a Deployment and why is it used?

📌 **Answer:**  
A Deployment manages replica sets and ensures desired state for pods.

🧠 **Why it matters:**  
Provides rolling updates, rollbacks, and self-healing.

---

## 5. Difference between Deployment, StatefulSet, and DaemonSet.

📌 **Answer:**  
- Deployment → Stateless apps
- StatefulSet → Stateful apps with stable identity
- DaemonSet → One pod per node

🛠️ **Example:**  
DaemonSet used for logging or monitoring agents.

---

## 6. What is a Service in Kubernetes?

📌 **Answer:**  
A Service exposes a set of pods as a network service.

Types:
- ClusterIP
- NodePort
- LoadBalancer

---

## 7. How does Kubernetes networking work?

📌 **Answer:**  
Every pod gets a unique IP. Pods communicate without NAT.

🧠 **Why it matters:**  
Simplifies service-to-service communication.

---

## 8. What is kube-proxy?

📌 **Answer:**  
kube-proxy maintains network rules to allow services to communicate with pods.

---

## 9. What is etcd and why is it critical?

📌 **Answer:**  
etcd is a distributed key-value store that stores cluster state.

⚠️ **Interview warning:**  
Losing etcd means losing cluster configuration.

---

## 10. What is a ConfigMap and Secret?

📌 **Answer:**  
- ConfigMap → Non-sensitive configuration
- Secret → Sensitive data like passwords

🧠 **Why it matters:**  
Separates config from application code.

---

## 11. Pod is stuck in Pending state. How do you debug?

🛠️ **Steps:**
```bash
kubectl describe pod <pod-name>
```
Check:
- Resource availability
- Node selectors
- PVC binding

---

## 12. Pod is in CrashLoopBackOff. What do you do?

📌 **Answer:**  
- Check logs:
```bash
kubectl logs <pod-name>
```
- Check events
- Validate image and command

---

## 13. How does Kubernetes handle scaling?

📌 **Answer:**  
- Manual scaling
- Horizontal Pod Autoscaler (HPA)
- Vertical Pod Autoscaler (VPA)

---

## 14. What is an Ingress?

📌 **Answer:**  
Ingress manages external HTTP/HTTPS access to services.

🧠 **Why it matters:**  
Centralized routing and TLS termination.

---

## 15. Node goes NotReady. What do you check?

📌 **Answer:**  
- kubelet status
- Node resources
- Network connectivity

---

## 16. How do you perform rolling updates in Kubernetes?

📌 **Answer:**  
Using Deployments with rolling update strategy.

🛠️ **Command:**
```bash
kubectl rollout status deployment <name>
```

---

## 17. How do you rollback a deployment?

📌 **Answer:**
```bash
kubectl rollout undo deployment <name>
```

---

## 18. What are taints and tolerations?

📌 **Answer:**  
Used to control pod scheduling on nodes.

🧠 **Use case:**  
Dedicated nodes for special workloads.

---

## 19. How do you secure a Kubernetes cluster?

📌 **Answer:**  
- RBAC
- Network Policies
- Pod Security Standards
- Secrets management

---

## 20. Kubernetes API server is not responding. What do you do?

🛠️ **Troubleshooting:**
- Check API server pod
- Check etcd
- Review control plane logs

---

📌 **Final Interview Tip:**  
Always explain Kubernetes answers in terms of **scalability, resilience, and automation**.
