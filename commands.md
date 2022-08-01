# Commands

### Namespace
```bash
# get namespaces
kubectl get namespaces

# create namespace
kubectl create namespace teszt

# create and use context
kubectl config set-context teszt --namespace=teszt
kubectl config use-context teszt
kubectl config current-context

# list contexts
kubectx

# change context
kubectx <CONTEXT>

# list namespece
kubens

# change namespace
kubens <NAMESPACE>
```

### Get
```bash
# list pods
kubectl get pods

# watch pods
watch kubectl get pods

# list all basic resources like pods, services configs ect., custom resources does not appear
kubectl get all
```

### Apply
```bash
# apply a manifest file
kubectl apply -f manifests/deployment.yaml

# apply all manifest files in current dir
kubectl apply -f .

# without syntax validate
kubectl apply -f my-app.yaml --validate=false
```

### Delete
```bash
# objektum tölése yaml-ből
kubectl delete -f valami.yaml

# adott pod törlése
kubectl delete pod <pod_neve>

# adott pod törlésének force-olása
kubectl delete pod <PODNAME> --grace-period=0 --force --namespace <NAMESPACE>

# összes pod törlése
kubectl delete pods --all
```

### Deployment rollout
```sh
kubectl rollout restart deployment/coredns
```

### Logs
```bash
kubectl logs app-67c6b5678b-j6gcn

# show logs continuously
kubectl logs -f app-67c6b5678b-j6gcn

# check init container logs
kubectl logs <pod> -c <init-container-neve>
# example
kubectl logs app-789d866576-bt58r -c init-config-container
```

### Pod information
```bash
# get information from pod
kubectl describe pod app-67c6b5678b-htt5x
```

### Port-forward
```bash
# port forward with kubectl, phpmyadmin:80 -> localhost:8080 
kubectl port-forward pod/phpmyadmin 80 8080
```

### Deployment scaling
```bash
kubectl scale deployment/my-app --replicas=0
```

### Secret creation
```bash
# docker secret creation
kubectl create secret docker-registry <pull_secret_name> \
    --docker-server=<registry_server> \
    --docker-username=<user_name> \
    --docker-password=<password> \
    --docker-email=<email>
```

### Copy data from container
```bash
# copy file from my PC to the pod
kubectl cp /root/my-local-file my-pod:/root/remote-filename

# copy to the the selected pod
kubectl cp /root/my-local-file my-namepace/my-pod:/root/remote-filename -c my-container

# Examples:
# !!!Important Note!!!
# Requires that the 'tar' binary is present in your container
# image.  If 'tar' is not present, 'kubectl cp' will fail.
#
# For advanced use cases, such as symlinks, wildcard expansion or
# file mode preservation consider using 'kubectl exec'.

# Copy /tmp/foo local file to /tmp/bar in a remote pod in namespace <some-namespace>
tar cf - /tmp/foo | kubectl exec -i -n <some-namespace> <some-pod> -- tar xf - -C tmp/bar

# Copy /tmp/foo from a remote pod to /tmp/bar locally
kubectl exec -n <some-namespace> <some-pod> -- tar cf - /tmp/foo | tar xf - -C /tmpbar

# Copy /tmp/foo_dir local directory to /tmp/bar_dir in a remote pod in the defaultnamespace
kubectl cp /tmp/foo_dir <some-pod>:/tmp/bar_dir

# Copy /tmp/foo local file to /tmp/bar in a remote pod in a specific container
kubectl cp /tmp/foo <some-pod>:/tmp/bar -c <specific-container>

# Copy /tmp/foo local file to /tmp/bar in a remote pod in namespace <some-namespace>
kubectl cp /tmp/foo <some-namespace>/<some-pod>:/tmp/bar

# Copy /tmp/foo from a remote pod to /tmp/bar locally
kubectl cp <some-namespace>/<some-pod>:/tmp/foo /tmp/bar
```