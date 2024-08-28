
### Verify the cluster to delete

```shell
kops get cluster
```

```shell
kops validate cluster --name demok8scluster.k8s.local
```

```shell
kubectl get nodes
```

### Destroy the cluster

> Running a kubernetes cluster within AWS obviously costs money, and so you may want to delete your cluster if you are finished running experiments.

```shell
kops delete cluster --name demok8scluster.k8s.local --yes
```

### Finally, verify the deleted cluster

```shell
kops get cluster
```

### Delete the bucket
