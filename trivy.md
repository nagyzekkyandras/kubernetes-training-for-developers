# Trivy

Trivy is a comprehensive security scanner. It is reliable, fast, extremely easy to use, and it works wherever you need it.

Trivy has different scanners that look for different security issues, and different targets where it can find those issues.

Targets:
- Container Image
- Filesystem
- Git repository (remote)
- Kubernetes cluster or resource

Scanners:
- OS packages and software dependencies in use (SBOM)
- Known vulnerabilities (CVEs)
- IaC misconfigurations
- Sensitive information and secrets

## Install
Linux:
```sh
apt-get install trivy
```
```sh
yum install trivy
```
MacOS
```sh
brew install aquasecurity/trivy/trivy
```
Use with docker
```sh
docker run aquasec/trivy
```

## Usage
```sh
# docker image scan 
trivy image python:3.4-alpine

# kubernetes cluster scan
trivy k8s --report summary cluster

# filesystem check
trivy fs --security-checks vuln,secret,config myfolder/

# check only high and critical severity, and create a junit-report.xml from the base template
trivy image --ignore-unfixed --severity HIGH,CRITICAL --format template --template "@contrib/junit.tpl" -o junit-report.xml "mydockerrepository/image:tag"
```
