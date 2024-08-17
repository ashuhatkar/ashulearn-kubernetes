## Kubernetes setup using Kubernetes Operations kOps on Amazon EC2 ##

Here are few resources and steps to get you started:

You'll learn how to:

1. Create a kubernetes cluster
2. Deploy an app:
3. Explorer your app:

### Create an EC2 instance or you can make use of your personal infrastructure (Debian, Ubuntu, and operating systems using apt/apt-get). ###

Pre-requisites:

1. AWS subscription
2. AWS command-line interface (CLI)
3. Python3
4. Kube command-line interface (Kubectl)

### Install dependencies: ###

> The command <mark>sudo get-apt update</mark> downloads package information from all configured sources.

```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl gnupg lsb-release software-properties-common
```

* Install the Apt repository signing keys, using the following commands:

(Ref: https://kubernetes.io/blog/2023/08/15/pkgs-k8s-io-introduction/)
> Download the public signing key for the Kubernetes package repositories. The same signing key is used for all repositories, so you can disregard the version in the URL:

```
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.28/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
```

> The above command prints out the line describing the relevant repository and this is piped to <mark>sudo tee</mark> as a way of writing to <mark>/etc/apt/sources.list.d/kubernetes.list</mark>. Replace the <mark>apt</mark> repository definition so that <mark>apt</mark> points to the new repository instead of the Google-hosted repository. Make sure to replace the Kubernetes minor version in the command below with the minor version you're currently using.

```
echo "deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

* Install the Python, AWS CLI, Kubectl workloads, using the following commands:

```
sudo apt-get update
sudo apt-get install -y python3-pip kubectl
```
> The above command <mark>sudo get-apt update</mark> downloads package information from all configured sources.

- For the latest version of the AWS CLI
```
pip3 install awscli --upgrade
```

- For the specific version of the AWS CLI
```
pip3 install awscli<1.6.312 --upgrade
```
> The above command install AWS CLI latest/specific version, using the pip3 command.

```
export PATH="$PATH:/home/ubuntu/.local/bin/"
```
> Set the path environment for the current session.

### Install kOps: ###

```
curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

chmod +x kops-linux-amd64

sudo mv kops-linux-amd64 /usr/local/bin/kops
```