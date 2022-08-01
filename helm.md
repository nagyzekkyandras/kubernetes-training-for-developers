# HELM

Helm uses a packaging format called charts. A chart is a collection of files (mostly yamls) that describe a related set of Kubernetes resources.

### The Chart File Structure
```
wordpress/
  Chart.yaml          # A YAML file containing information about the chart
  LICENSE             # OPTIONAL: A plain text file containing the license for the chart
  README.md           # OPTIONAL: A human-readable README file
  values.yaml         # The default configuration values for this chart
  values.schema.json  # OPTIONAL: A JSON Schema for imposing a structure on the values.yaml file
  charts/             # A directory containing any charts upon which this chart depends.
  crds/               # Custom Resource Definitions
  templates/          # A directory of templates that, when combined with values,
                      # will generate valid Kubernetes manifest files.
  templates/NOTES.txt # OPTIONAL: A plain text file containing short usage notes
```

## Commands

### usage 
```sh
# create a chart chart
helm create <NAME>

# add the repository
helm repo add nagyzekkyandras https://nagyzekkyandras.github.io/helm/

# search in the repository
helm search repo nagyzekkyandras

# search in the repository with all versions
helm search repo nagyzekkyandras -l

# update your local repositories metadata
helm repo update

# install from the helm repository (without downloading it)
helm install nginx-hello nagyzekkyandras/nginx-hello --version 0.0.1 -f my-values.yaml

# install / upgrade from chart local folder
helm upgrade --install -f my-values.yaml --set name=nginx-hello nginx-hello ./nginx-hello

# delete installed chart
helm uninstall nginx-hello

# syntax check
helm lint mychart/
helm lint mychart/ --strict --with-subcharts

# generate template (for debugging)
helm template mychart/
helm template -f my-values.yaml my-chart-name my-chart/

# create tgz package for nexus or other repositories
helm package my-chart/

# check history
helm history release-name -o yaml
helm history release-name --debug

# get installed chart values
helm get values <NAME>
```