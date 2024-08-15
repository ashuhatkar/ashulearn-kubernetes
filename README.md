
# Kubernetes

## Kubernetes Cluster Architecture: ##

![Kubernetes cluster architecture definitions](https://kubernetes.io/images/docs/kubernetes-cluster-architecture.svg)

## Kube Master Node Components ##

| Component | Description |
| --------- | ----------- |
| **Etcd** | This is a data store used by Kubernetes to store all information about the cluster. It’s critical for keeping everything up to date |
| **kube-apiserver** | This component exposes Kubernetes API to users allowing them to create API resources, run applications, and configure various parameters of the cluster.|
| **kube-controller-manager** | The component that manages API objects created by users. It makes sure that the actual state of the cluster always matches the desired state |
| **kube-scheduler** | This component is responsible for scheduling user workloads on the right infrastructure. When scheduling applications, kube-scheduler considers various factors such as available node resources, node health, and availability, as well as user-defined constraints.|
| **cloud-controller-manager** | This component embraces various controllers, all of which interact with the cloud providers’ APIs.|


## Kube Worker Node Components ##

| Component | Description |
| --------- | ----------- |
| **kube-proxy** | kube-proxy is a network proxy that runs on each node in your cluster. kube-proxy maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster. |
| **kubelet** | The kubelet is the primary “node agent” that runs on each node & manages the containers/pods running on each node |
| **Container Runtime** | A container runtime is software that executes containers and manages container images on a node. Today, the most widely known container runtime is Docker, but there are other container runtimes in the ecosystem, such as rkt, containerd, and lxd |
