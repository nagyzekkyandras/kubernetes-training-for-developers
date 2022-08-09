# ETCD

Etcd is defined as “a strongly consistent, distributed key-value store that provides a reliable way to store data that needs to be accessed by a distributed system or cluster of machines.” One of the most notable uses is the management of configuration data, state data and metadata for Kubernetes.

- Fully replicated: every node in an etcd cluster has access to the full data store.
- Highly available: there is no single point of failure and it gracefully tolerates hardware failures and network partitions
- Reliably consistent: every data “read” returns the latest data “write” across all clusters
- Fast: supports 10,000 writes per second
- Simple: any application, from simple web apps to complex container orchestration engines such as Kubernetes, can read or write data to etcd using standard HTTP/JSON  tools
- Secure: etcd supports automatic transport layer security (TLS) and optional secure socket layer (SSL) client certificate authentication

## Commands
```sh
# list users
etcdctl user list

# create user
etcdctl user add <user>
# create user with password
etcdctl user add <user> --new-user-password=<password>

# add user to role
etcdctl user grant-role <user> <role>

# authentication enable
etcdctl auth enable
# authentication disable
etcdctl --user <user>:<password> auth disable

# get all in the etcd database
etcdctl get --prefix ""

# get all in the etcd database with auth
etcdctl --user root get --prefix ""
etcdctl --user <user>:<password> get --prefix ""

# delete all in the etcd database
etcdctl del "" --from-key=true

# create a key value
etcdctl put <key> <value>
etcdctl put private.andras.test.no.expiry 30

# get a value of a private / protected / public key
etcdctl get private.andras.test.no.expiry --print-value-only

# save db to snapshot
etcdctl snapshot save <filename>
etcdctl snapshot save my.db
etcdctl --write-out=table snapshot status my.db
```