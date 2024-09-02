
## Updates and Upgrades

#### PROCESS
1. It takes the Master node\s first, and upgrades the Master node to the specified Kubernetes version.
2. Then it goes to the Worker nodes and does the upgrade. It upgrades the worker nodes one by one.
   1. Drains all the pods that are currently running on that node.
   2. It waits for the pods to be evicted, and then it disables that node, so that no new pods get scheduled to that node.
   3. Takes the node offline, upgrades the node, and brings the node back online.
   4. Once it has verified that the node has come-up and is back in service, it will then go to the next node and upgrade the node.

### **`Upgrading Kubernetes to a specific version`**

The cluster spec contains a `kubernetesVersion`, so you can simply edit it with `kops edit`, and apply the updated configuration to your cluster.

It is recommended to run the latest version of kOps to ensure compatibility with the target kubernetesVersion. When applying a Kubernetes minor version upgrade (e.g. `v1.16.0` to `v1.16.3`), you should confirm that the target kubernetesVersion is compatible with the current [kOps release](https://github.com/kubernetes/kops/releases).

### `Manual update`

`Steps`:

1. kops edit cluster - edit the cluster configuration, and specify what kubernetes version to be upgrade.
2. kops update cluster - update the cluster state.
3. kops rolling-update - PROCESS

### Verify the cluster

```shell
kops get cluster
```

### Step 1: Edit cluster

```shell
kops edit cluster --name demok8scluster.k8s.local
```

Set the KubernetesVersion to the target version (e.g. `1.16.3`)

### Check kubernetes server version

```sh
kubectl version --short
kubectl get nodes
```

### Step 2: Update cluster

**Note the verb used below is `update` not `upgrade`**

```sh
kops update cluster --name demok8scluster.k8s.local --yes
```

### Step 3: Rolling-update

```sh
kops rolling-update cluster --name demok8scluster.k8s.local --yes
```

### Verify cluster

```sh
kops validate cluster --name demok8scluster.k8s.local
kubectl get nodes
kubectl version --short
```

We have successfully upgraded kubernetes cluster from `1.16.0` to `1.16.3`.

### **`Upgrading Kubernetes to latest version`**

### `Automated update`

`Steps`:

1. kops upgrade cluster - upgrade the cluster configuration to the latest vesion supported by the kops version.
2. kops update cluster - update the cluster state.
3. kops rolling-update - PROCESS

### Verify the cluster

```shell
kops get cluster
```

### Step 1: Upgrade cluster

**Note the verb used below is `upgrade` not `update`**

```sh
kops upgrade cluster --name demok8scluster.k8s.local --yes
```
Updates are applied to the configuration and now we are ready to apply these changes, using:

### Step 2: Update cluster

```sh
kops update cluster --name demok8scluster.k8s.local --yes
```

### Step 3: Rolling-update

```sh
kops rolling-update cluster --name demok8scluster.k8s.local --yes
```

### Verify cluster

```sh
kops validate cluster --name demok8scluster.k8s.local
kubectl get nodes
kubectl version --short
```

We have successfully upgraded kubernetes cluster from `1.16.3` to the ***latest version***.