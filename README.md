## What Is Kyverno?

**Kyverno** is a **Kubernetes-native policy engine** that helps you **enforce, mutate and generate** Kubernetes resources — all using **YAML, not code**.

It’s designed for **Kubernetes admins** and **DevOps engineers**, not developers or programmers.

> 🧠 Think of Kyverno as a “policy controller” that automatically checks or fixes Kubernetes objects when they are created, updated, or deleted.

---

### 🧱 Kyverno Architecture

Kyverno runs inside your cluster as a set of **controllers and admission webhooks**:

| Component | Function |
|------------|-----------|
| **Admission Controller** | Validates or mutates resources when they’re applied |
| **Background Controller** | Periodically scans existing resources for compliance |
| **Cleanup Controller** | Deletes resources automatically based on rules |
| **CRDs (Custom Resource Definitions)** | Define Kyverno policies like `ClusterPolicy`, `Policy`, and `PolicyReport` |

---

### ⚙️ Kyverno Policy Types

Kyverno supports three main types of rules inside a policy:

| Type | Purpose | Example |
|------|----------|----------|
| **Validate** | Check and block if rule not met | “Pods must have label `app`” |
| **Mutate** | Automatically add or modify fields | “Add `team: devops` label if missing” |
| **Generate** | Create new resources automatically | “Generate a `NetworkPolicy` for each namespace” |

---

### 📘 Kyverno Policy Resources

Kyverno defines two main kinds of policies:

| Resource | Scope | Description |
|-----------|--------|--------------|
| **Policy** | Namespace-level | Applies to resources within a specific namespace |
| **ClusterPolicy** | Cluster-wide | Applies to all namespaces and cluster-scoped resources |

---

### 🏗️ Example Use Cases

- Enforce security best practices (non-root containers, signed images)
- Automatically generate default `NetworkPolicy` in each namespace
- Add missing labels or annotations to Pods
- Audit and report non-compliant resources

---

### 🧩 validationFailureAction

The `validationFailureAction` field in Kyverno policies determines **how the policy engine reacts when a validation rule fails**.

#### 🔧 Behavior Options

| Value | Behavior |
|--------|-----------|
| **enforce** | ❌ Rejects the resource — a **hard block** preventing it from being created or updated. |
| **audit** | ⚠️ Only reports the violation — a **soft warning**, allowing the resource to be created but logged as non-compliant. |

---

### 🧠 Key Kyverno Features

Kyverno provides a powerful, Kubernetes-native way to **govern your cluster configuration, security, and compliance** — all through declarative YAML policies.

| Feature | Description |
|------------------------------|--------------|
| ✅ **Policy as Code (YAML)** | Write policies just like standard Kubernetes manifests |
| 🔄 **Admission Control** | Validate or mutate live API requests before they’re persisted |
| 🕵️‍♀️ **Background Scanning** | Continuously checks existing resources for policy compliance |
| 🧬 **Auto Remediation** | Automatically fixes or generates missing resources |
| 📊 **Policy Reports** | Produces compliance reports via CRDs like `PolicyReport` |
| 🔐 **Pod Security Enforcement** | Easily apply Pod Security Standards (PSP-like controls) |
| 💾 **GitOps Friendly** | Fully compatible with ArgoCD and Flux for declarative policy management |

---

### 🧰 Real-World Use Cases

| Use Case | Example Policy |
|-----------|----------------|
| **Security Hardening** | Enforce non-root or non-privileged containers |
| **Compliance** | Require mandatory labels such as `team` or `environment` |
| **Networking** | Automatically generate a `NetworkPolicy` in each namespace |
| **Resource Management** | Apply default `LimitRange` or `ResourceQuota` settings |
| **Governance** | Block usage of disallowed image tags (e.g., `:latest`) |

---

### 🚀 Why Kyverno?

- 🧩 Native to Kubernetes — no external policy language needed  
- 🔐 Strengthens security posture through declarative guardrails  
- 📈 Enhances visibility and compliance with detailed reports  
- 💡 Simplifies cluster governance for DevOps and platform teams  

---

### 🚀 Learn More

- [Kyverno Official Docs](https://kyverno.io/docs/)
- [Kyverno GitHub Repository](https://github.com/kyverno/kyverno)
- [Kyverno Policies Library](https://kyverno.io/policies/)

---
