# Kubernetes training for developers

### High level overview:
![components-of-kubernetes](images/components-of-kubernetes.svg)
source: https://kubernetes.io/docs/concepts/overview/components/

- Node = Worker node
- Control Plane = Master nodes

### Node level overview:
- Kubernetes
- Container runtime
- OS (mostly linux)

### Workloads
- Deployments
- Statefulsets
- DaemonSets
- Jobs
- CronJobs
- Pods

### Storage
- Storage Classes
- Persistance Volumes
- Persistance Volume Claims

### Configuration
- Config Maps
- Secrets

Secret managers

**Hashicorp Vault**

Secure, store and tightly control access to tokens, passwords, certificates, encryption keys for protecting secrets and other sensitive data using a UI, CLI, or HTTP API.

### Network
- Services
- Endpoints
- Ingress

Service mesh (service networking layer)

**Istio**
- Secure cloud-native apps
- Manage traffic effectively
- Monitor service mesh
- Simplify load balancing with advanced features
- Enforce policies

### Custom resources
- Istio
    - authorizationpolicies
    - destinationrules
    - envoyfilters
    - gateways
    - istiooperators
    - peerauthentications
    - requestauthentications
    - serviceentries
    - sidecars
    - telemetries
    - virtualservices
    - wasmplugins
    - workloadentries
    - workloadgroups

### Tools
| Name | Description |
|---|---|
|kubectl | The Kubernetes command-line tool, kubectl, allows you to run commands against Kubernetes clusters. https://github.com/kubernetes/kubectl |
|kubectx / kubens | Faster way to switch between clusters and namespaces in kubectl. https://github.com/ahmetb/kubectx |
|helm | The package manager for Kubernetes. https://github.com/helm/helm |
|lens | Kubernetes Lens is an effective, open-source IDE for Kubernetes. https://github.com/lensapp/lens |

[Basic kubectl (+ kubectx and kubens) commands.](./commands.md)

[Helm basics.](./helm.md)