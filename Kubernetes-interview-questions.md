# 🔹 **Karpenter**

### Basic:

* What is Karpenter and what problem does it solve?

### Intermediate:

* How does Karpenter differ from the Kubernetes Cluster Autoscaler?
* Explain Karpenter’s architecture and key CRDs (Provisioner, NodeTemplate, etc.).
* How do you configure Karpenter to prefer Spot instances and fall back to On-Demand?

### Advanced:

* How does Karpenter decide to scale up and how does it bin-pack pods?
* How do you restrict Karpenter to provision nodes only in certain subnets, AZs, or instance types?
* How do taints/tolerations and nodeSelectors/nodeAffinity interact with Karpenter provisioning?
* Troubleshooting: a pod remains Pending — how do you debug whether Karpenter should have provisioned capacity?

---

# 🔹 **Istio**

### Basic:

* What is Istio and what are the core problems it addresses?
* What are sidecar proxies in Istio and how are they injected?

### Intermediate:

* Explain VirtualService, DestinationRule and Gateway — when do you use each?
* How does Istio implement mutual TLS between services? How do you enable/disable it?
* How do you implement traffic splitting/canary releases with Istio?

### Advanced:

* How does Istio interact with Kubernetes NetworkPolicies and CNI plugins?
* Debugging: how would you approach tracing/metrics/logging when traffic is being rejected by Istio?
* How does Istio handle egress traffic and external services?

---

# 🔹 **AWS (General + EKS)**

### Basic:

* Describe IAM roles vs policies. How are they used with EKS worker nodes and pods?
* What are the main differences between EC2, EKS, and Fargate?

### Intermediate:

* How would you design networking for an EKS cluster across multiple AZs (subnets, route tables, NAT, IGW)?
* What are best practices for storing secrets in AWS for Kubernetes workloads?
* How do you monitor and alert on cluster health and pod/application metrics in AWS?

### Advanced:

* How does the AWS VPC CNI plugin assign Pod IPs and what are common IP exhaustion problems and mitigations?
* Explain how you would migrate an on-prem cluster to EKS with minimal downtime.

---

# 🔹 **Kubernetes – Core Concepts**

### Basic:

* Describe the Kubernetes control plane components and their responsibilities.
* What is a Pod and how does it differ from a container?
* Explain Deployments, ReplicaSets, StatefulSets and DaemonSets and when to use each.

### Intermediate:

* Explain livenessProbe vs readinessProbe and common misconfigurations.
* How does rolling update work for a Deployment? How to perform a rollback?
* Explain ConfigMap and Secret — how to mount/use them safely.
* How do RBAC roles and roleBindings work in Kubernetes? How to secure the API?

### Advanced:

* Explain StorageClasses, PersistentVolumes, PersistentVolumeClaims and dynamic provisioning.
* How do you design pod resource requests/limits and what are the consequences of misconfiguration?
* How do Kubernetes Admission Controllers work? Give examples where you would use them.

---

# 🔹 **Kubernetes – Pod Networking (Expanded)**

### Basic:

* How do pods get their IP addresses in Kubernetes?
* What is a CNI plugin and why is it necessary?

### Intermediate:

* How does pod-to-pod communication work across nodes?
* What is the difference between hostNetwork: true and using the normal pod network?
* How does DNS resolution (CoreDNS) work for Services and pods?
* What are NetworkPolicies and how do they control traffic?
* What are common troubleshooting commands and techniques for pod-networking issues?
* Explain NAT/SNAT behavior for outbound pod traffic in various CNI implementations.
* How do NodePort and LoadBalancer services map to underlying node/cluster networking?
* What is hairpin NAT and when might it affect your workloads?

### Advanced:

* Compare kube-proxy modes (iptables vs IPVS) — tradeoffs and performance implications.
* Explain how the AWS VPC CNI (amazon-vpc-cni-k8s) works; how are pod IPs mapped to ENIs?
* How does Cilium (eBPF-based CNI) differ from traditional iptables-based CNIs?
* How do you implement and test a NetworkPolicy that allows only certain namespaces/pods to talk to a database pod?
* Describe common MTU-related problems in pod networking and how to detect/fix them.
* Explain Pod IP lifecycle — what happens to IPs when pods restart, reschedule, or nodes are terminated?
* How do you troubleshoot intermittent packet drops between pods on different nodes? (tools, what to inspect: routes, ARP, iptables, conntrack, CNI logs)
* How do service meshes (e.g., Istio) affect pod networking (iptables sidecar rules, redirected ports) and what problems can arise?
* How would you handle multi-network (Multus) or multiple interfaces for pods?
* What changes are needed when running stateful workloads requiring stable network identity (headless services, DNS, StatefulSets)?
* How does Kubernetes implement Service IP routing vs direct pod IP routing (clusterIP vs endpointRouting)?
* How do you debug LB source IP preservation and how to enable/provide it (externalTrafficPolicy, proxy protocol, X-Forwarded-For)?
* Scenario: Pod A in node1 cannot reach Service B (ClusterIP) — list step-by-step checks you would perform.

---

# 🔹 **Helm Charts**

### Basic:

* What is Helm and what are charts?
* Explain Chart.yaml, values.yaml, templates/ directory.

### Intermediate:

* How do you handle different environments (staging/prod) with Helm?
* Explain hooks in Helm and use cases for pre-install/post-install hooks.
* How do you manage chart dependencies and subcharts?
* How do you test and validate Helm charts before deployment?

### Advanced:

* How would you design a reusable chart supporting optional subcomponents, secrets, and upgrade safety?
* How do you handle sensitive values in values.yaml securely?
* Troubleshooting: how to debug a failing upgrade/rollback?

---

# 🔹 **Scenario-Based / Troubleshooting**

* A deployment upgrade caused all pods to fail readiness checks — how do you rollback and investigate root cause?
* An application is slow and profiling shows network latency spikes between services — how do you narrow down whether it's app, Kubernetes network, or infrastructure?
* Pods intermittently lose connectivity after node scale-in — how do you investigate and resolve?
* Post-deployment of Istio, some services can’t talk to each other though NetworkPolicies allow it — how do you debug the interaction?
* You need to reduce cloud costs for EKS workloads; what steps would you take (Karpenter, instance types, Spot, rightsizing, scheduling)?

---


