# Kubernetes training for developers
Kubernetes is an open-source container orchestration system for automating software deployment, scaling, and management.

### High level overview:
![components-of-kubernetes](images/components-of-kubernetes.svg)

source: https://kubernetes.io/docs/concepts/overview/components/

- Node = Worker node
- Control Plane = Master nodes

### Node level overview:
- Kubernetes
- Container runtime
    - containerd
    - CRI-O
    - Docker Engine
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
    - allowVolumeExpansion
- Persistance Volumes
    - Volume Mode
        - Filesystem
        - Block
    - Access Modes
        - RWO - ReadWriteOnce
        - ROX - ReadOnlyMany
        - RWX - ReadWriteMany
        - RWOP - ReadWriteOncePod
- Persistance Volume Claims

### Configuration
- Config Maps
- Secrets
- Secret managers
    - Hashicorp Vault
        - Secure, store and tightly control access to tokens, passwords, certificates, encryption keys for protecting secrets and other sensitive data using a UI, CLI, or HTTP API.

### Network
- Services
- Endpoints
- Ingress
    - Service mesh (service networking layer)
        - Istio
            - Secure cloud-native apps
            - Manage traffic effectively
            - Monitor service mesh
            - Simplify load balancing with advanced features
            - Enforce policies

### Custom resources
- Istio used / created custom resources
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
|Rancher Desktop | Container Management and Kubernetes on the Desktop https://github.com/rancher-sandbox/rancher-desktop/ |
|oc | The OpenShift Command Line, part of OKD https://github.com/openshift/oc |
|source-to-image | A tool for building artifacts from source and injecting into container images for Openshift https://github.com/openshift/source-to-image |

### Commands
- [Basic kubectl (+ kubectx and kubens) commands.](./commands.md)
- [Useful administrator commands.](./administrator_commands.md)
- [Basic helm commands.](./helm.md)
- [Basics of Openshift and commands.](./openshift.md)
- [Basic etcd commands.](./etcd.md)
- [Basics of GCP.](./gcp.md)