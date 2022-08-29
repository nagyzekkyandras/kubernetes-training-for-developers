# Nova
Find outdated or deprecated Helm charts running in your cluster.

Nova scans your cluster for installed Helm charts, then cross-checks them against all known Helm repositories. If it finds an updated version of the chart you're using, or notices your current version is deprecated, it will let you know.

Nova can also scan your cluster for out of date container images.

## Install
MacOS:
```sh
brew install fairwindsops/tap/nova
```
Linux
```sh
curl -L "https://github.com/FairwindsOps/nova/releases/download/3.2.0/nova_3.2.0_linux_amd64.tar.gz" > nova.tar.gz
tar -xvf nova.tar.gz
sudo mv nova /usr/local/bin/
```

## Usage
```sh
# scan the currently selected cluster and checks the helm chart versions
nova find
# more detailed view with all namespace
nova find --wide

# define desired versions
nova find --desired-versions='metrics-server=6.0.0,swagger-ui=12.0.0'
# file defined desired versions
nova find --config manifests/nova.yaml

# check the containers
nova find --containers
# checks in all namespace
nova find --containers --wide

# change the context
nova find --context DEV-CLUSTER
```