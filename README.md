# Kubernetes

## Kubernetes Cluster Architecture:

![Kubernetes cluster architecture definitions](https://kubernetes.io/images/docs/kubernetes-cluster-architecture.svg)

## Kube Master Node Components (Control plane)

| Component                          | Description                                                                                                                                                                                                                                                           |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **kube-apiserver**                 | This component exposes Kubernetes API to users allowing them to create API resources, run applications, and configure various parameters of the cluster.                                                                                                              |
| **Etcd**                           | This is a data store used by Kubernetes to store all information about the cluster. It’s critical for keeping everything up to date.                                                                                                                                  |
| **kube-scheduler**                 | This component is responsible for scheduling user workloads on the right infrastructure. When scheduling applications, kube-scheduler considers various factors such as available node resources, node health, and availability, as well as user-defined constraints. |
| **kube-controller-manager**        | The component that manages API objects created by users. It makes sure that the actual state of the cluster always matches the desired state.                                                                                                                         |
| **cloud-controller-manager (opt)** | This component embraces various controllers, all of which interact with the cloud providers’ APIs.                                                                                                                                                                    |

## Kube Worker Node Components

| Component             | Description                                                                                                                                                                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **kubelet**           | The kubelet is the primary “node agent” that runs on each node & manages the containers/pods running on each node                                                                                                                        |
| **Container Runtime** | A container runtime is software that executes containers and manages container images on a node.                                                                                                                                         |
| **kube-proxy (opt)**  | kube-proxy is a network proxy that runs on each node in your cluster. kube-proxy maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster. |

<!-- markdown-link-check-disable -->

## Setup kubernetes cluster on EC2 instance using kOps

> [!NOTE]
> Sets up the latest kubernetes version:
>
> [install-kubernetes-with-kops-on-amzn-ec2](https://github.com/ashuhatkar/ashulearn-provisioning-kubernetes-on-prod-systems/blob/develop/01-install/install-kubernetes-with-kops-on-amzn-ec2.md)
>
> [upgrade-kubernetes-with-kops-on-amzn-ec2](https://github.com/ashuhatkar/ashulearn-provisioning-kubernetes-on-prod-systems/blob/develop/02-upgrade/upgrade-kubernetes-with-kops-on-amzn-ec2.md)
>
> [scaling-kubernetes-with-kops-on-amzn-ec2](https://github.com/ashuhatkar/ashulearn-provisioning-kubernetes-on-prod-systems/blob/develop/03-scale/scaling-kubernetes-with-kops-on-amzn-ec2.md)
>
> [deleting-kubernetes-with-kops-on-amzn-ec2](https://github.com/ashuhatkar/ashulearn-provisioning-kubernetes-on-prod-systems/blob/develop/04-delete/deleting-kubernetes-with-kops-on-amzn-ec2.md)

## Manage kubernetes cluster using EKS and Terraform

<!-- markdown-link-check-enable -->

> [!NOTE]
> Sets up the latest kubernetes version:
>
> [install-kubernetes-with-terraform-and-eks](https://github.com/ashuhatkar/ashulearn-provisioning-kubernetes-on-prod-systems/blob/develop/01-install/install-kubernetes-with-terraform-eks-on-amzn.md)
