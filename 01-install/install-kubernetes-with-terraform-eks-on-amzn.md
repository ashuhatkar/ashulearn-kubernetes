## Kubernetes setup using Terraform and EKS

`Here are few resources and steps to get you started`:

`You'll learn how to`:

1. Create cluster
2. Manage cluster

`Pre-requisites`:

1. AWS subscription
2. AWS command-line interface (AWS CLI)
3. Eksctl command-line interface (CLI)
4. Terraform

### `Setup your environment`

### Install dependencies (LINUX - Ubuntu/Debian)

[Setup](https://docs.aws.amazon.com/eks/latest/userguide/setting-up.html)

### Configure AWS CLI

```sh
aws configure
```

### Setup kubectl and eksctl binary

```sh
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.30.2/2024-07-12/bin/linux/arm64/kubectl
chmod +x ./kubectl
mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
```

```sh
# for ARM systems, set ARCH to: `arm64`, `armv6` or `armv7`
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH

curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

# (Optional) Verify checksum
curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz

sudo mv /tmp/eksctl /usr/local/bin
```

### Verify the installs

```sh
kubectl version
eksctl version
```

Eksctl uses the credentials from the AWS CLI to connect to your account.

### Spin up a cluster

```sh
eksctl create cluster \
  --name demok8scluster.k8s.local \
  # default node-type if not specified - m5-large instance \
  --node-type t2.micro \
  --nodes 3 \
  --nodes-min 3 \
  --nodes-max 5 \
  --region eu-central-1
```

### Verify cluster

```sh
eksctl get cluster \
   --name demok8scluster.k8s.local \
   --region eu-central-1

kubectl get nodes -o wide
```

### Delete cluster

```sh
eksctl delete cluster \
   --name demok8scluster.k8s.local \
   --region eu-central-1
```

### `Provision an EKS cluster with Terraform`

### Install Terraform

```sh
sudo apt-get update
sudo apt-get install -y curl gnupg lsb-release software-properties-common
```

```shell
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
```

### Verify the install

```sh
terraform -help
```