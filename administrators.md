# Usefull admin commands
```sh
# check kubernetes API health endpoints
kubectl get --raw='/readyz?verbose'

# label a namespace
kubectl label namespace <my-namespace> istio-injection=enabled
kubectl label namespace <my-namespace> istio-injection=enabled --overwrite

# patch a persistentVolumeReclaimPolicy value on a PV from Delete to Retain
kubectl patch pv pvc-3e953bf9-25c4-499d-ae09-d23d0f9f6c44 -p '{"spec":{"persistentVolumeReclaimPolicy":"Retain"}}'
```