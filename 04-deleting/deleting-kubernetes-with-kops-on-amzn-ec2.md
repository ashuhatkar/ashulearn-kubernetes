### Destroy the cluster

> Running a kubernetes cluster within AWS obviously costs money, and so you may want to delete your cluster if you are finished running experiments.

```shell
kops delete cluster --name demok8scluster.k8s.local --yes
```

### Verify the cluster

```shell
kops get cluster
```