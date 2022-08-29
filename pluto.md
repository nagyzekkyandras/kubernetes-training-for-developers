# Pluto
Pluto is a utility to help users find deprecated Kubernetes apiVersions in their code repositories and their helm releases.

## Install
MacOS
```
brew install FairwindsOps/tap/pluto
```
Linux
https://github.com/FairwindsOps/pluto/releases

## Usage
```sh
# scan directory
pluto detect-files -d <FOLDER>

# detect in installed helm charts in all namespaces
pluto detect-helm -owide

# select specific namespace
pluto detect-helm -n <NAMESPACE> -owide

# put the result in CSV file
pluto detect-helm -o csv

# check with specific kubernetes version
pluto detect-helm --target-versions k8s=v1.15.0
```