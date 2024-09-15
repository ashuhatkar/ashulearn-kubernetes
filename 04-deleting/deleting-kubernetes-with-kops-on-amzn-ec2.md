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

### Cleanup the cluster

> Running a kubernetes cluster within AWS obviously costs money, and so you may want to delete your cluster if you are finished running experiments.

```shell
kops delete cluster --name demok8scluster.k8s.local --yes
```

### Finally, verify the deleted cluster

```shell
kops get cluster
```

### Delete the S3 bucket

> When versioning is enabled, a simply DELETE cannot permanently delete an object. Instead, Amazon S3 inserts a delete marker.

![Delete request use cases](https://docs.aws.amazon.com/images/AmazonS3/latest/userguide/images/versioning_DELETE_versioningEnabled.png)

> To delete versioned objects permanently.

![Delete request use cases](https://docs.aws.amazon.com/images/AmazonS3/latest/userguide/images/versioning_DELETE_versioningEnabled2.png)

- The following command deletes an object named test.txt from a bucket named amzn-s3-demo-bucket1. To remove a specific version of an object, you must be the bucket owner and you must use the version Id subresource.

```shell
# aws s3api delete-object --bucket amzn-s3-demo-bucket1 --key test.txt --version-id versionID
aws s3api delete-object --bucket kops-ashu-storage --key test.txt --version-id versionID

aws s3 rb s3://bucket-name --force
```
