## Kubernetes setup using EKS and Terraform

`Here are few resources and steps to get you started`:

`You'll learn how to`:

1. Create cluster
2. Manage cluster

`Pre-requisites`:

1. AWS subscription
2. AWS command-line interface (AWS CLI)
3. eksctl command-line interface (CLI)
4. kubectl
4. Terraform

### `Setup your environment`

### Install dependencies (LINUX - Ubuntu/Debian)

[Setup](https://docs.aws.amazon.com/eks/latest/userguide/setting-up.html)

### Configure AWS CLI

```sh
aws configure
```

### Setup kubectl and eksctl binary

## Install or update kubectl

kubectl is a command line tool that you use to communicate with the Kubernetes API server.

***Note***
You must use a kubectl version that is within one minor version difference of your Amazon EKS cluster control plane. For example, a `1.29 kubectl client` works with Kubernetes `1.28`, `1.29`, and `1.30` clusters.

```sh
curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.30.2/2024-07-12/bin/linux/arm64/kubectl
chmod +x ./kubectl
mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH
```

eksctl

***Prerequisite***:

You will need to have AWS API credentials configured. What works for AWS CLI or any other tools (kops, Terraform, etc.) should be sufficient. You can use `~/.aws/credentials file` or `environment variables`.

You will also need AWS IAM Authenticator for Kubernetes command (either `aws-iam-authenticator` or `aws eks get-token` (available in version 1.16.156 or greater of AWS CLI) in your `PATH`.

The IAM account used for EKS cluster creation should have these minimal access levels.

1) Cloud formation - Full access.
2) EC2 - ***Full***: Tagging ***Limited***: List, Read, Write
3) EC2 Auto Scaling - ***Limited***: List, Write
4) EKS - Full Access
5) IAM - ***Limited***: List, Read, Write, Permissions Management
6) Systems Manager - ***Limited***: List, Read

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

### Step 1. Spin up a Amazon EKS cluster and nodes.

Create your Amazon EKS cluster with the following command. You can replace ***my-cluster-name*** with your own value. The name can contain only alphanumeric characters (case-sensitive) and hyphens. It must start with an alphanumeric character and can't be longer than 100 characters. The name must be unique within the AWS Region and AWS account that you're creating the cluster in. Replace ***region-code*** with any AWS Region that is supported by Amazon EKS.

- This example command creates a cluster named prod in your default region using aws cli.

```sh
aws eks create-cluster --name prod \
  --role-arn arn:aws:iam::012345678910:role/eks-service-role-AWSServiceRoleForAmazonEKS-J7ONKE3BQ4PI \
  --resources-vpc-config subnetIds=subnet-6782e71e,subnet-e7e761ac,securityGroupIds=sg-6979fe18
```

- To create a new cluster with private endpoint access and logging enabled using aws cli. This example command creates a cluster named example in your default region with public endpoint access disabled, private endpoint access enabled, and all logging types enabled.

```sh
aws eks create-cluster --name example --kubernetes-version 1.12 \
  --role-arn arn:aws:iam::012345678910:role/example-cluster-ServiceRole-1XWBQWYSFRE2Q \
  --resources-vpc-config subnetIds=subnet-0a188dccd2f9a632f,subnet-09290d93da4278664,subnet-0f21dd86e0e91134a,subnet-0173dead68481a583,subnet-051f70a57ed6fcab6,subnet-01322339c5c7de9b4,securityGroupIds=sg-0c5b580845a031c10,endpointPublicAccess=false,endpointPrivateAccess=true \
  --logging '{"clusterLogging":[{"types":["api","audit","authenticator","controllerManager","scheduler"],"enabled":true}]}'
```

- To create a new cluster using eksctl tool.

```sh
eksctl create cluster \
  --name <my-cluster-name> \
  # default node-type if not specified - m5-large instance \
  --node-type t2.micro \
  --nodes 3 \
  --nodes-min 3 \
  --nodes-max 5 \
  --region <region-code>
  --fargate
```

eksctl creates a `kubectl` `config` file in `~/.kube` or adds the new cluster's configuration within an existing config file in ~/.kube on your computer.

### Step 2. Verify cluster

```sh
eksctl get cluster \
   --name <my-cluster-name> \
   --region <region-code>

kubectl get nodes -o wide
```

### Step 3. Delete cluster and nodes

```sh
eksctl delete cluster \
   --name <my-cluster-name> \
   --region <region-code>
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