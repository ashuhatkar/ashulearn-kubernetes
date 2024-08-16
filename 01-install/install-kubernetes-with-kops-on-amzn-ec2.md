## Kubernetes setup using Kubernetes Operations kOps on Amazon EC2 ##

Here are few resources and steps to get you started:

You'll learn how to:

1. Create a kubernetes cluster
2. Deploy an app:
3. Explorer your app:

### Create an EC2 instance or you can make use of your personal infrastructure. ###

Pre-requisites:

1. AWS subscription
2. AWS command-line interface (CLI)
3. Python3
4. Kube command-line interface (Kubectl)

### Install dependencies: ###

* Install the Apt repository signing keys, using the following commands:

```
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```
> The command downloads a gpg signature from <mark>https://packages.cloud.google.com/apt/doc/apt-key.gpg</mark> which is then piped to <mark>sudo apt-key add -</mark> (the - mean "read from standard input") which adds the key to the list of known apt keys.

```
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
```
> The command prints out the line describing the relevant repository and this is piped to <mark>sudo tee</mark> as a way of writing to <mark>/etc/apt/sources.list.d/kubernetes.list</mark>.

* Install the Python, AWS CLI workloads, using the following commands:

```
sudo apt-get update
sudo apt-get install -y python3-pip apt-transport-https kubectl
```
> The command <mark>sudo get-apt update</mark> downloads package information from all configured sources.

- For the latest version of the AWS CLI
```
pip3 install awscli --upgrade
```

- For the specific version of the AWS CLI
```
pip3 install awscli<1.6.312 --upgrade
```
> The command install AWS CLI latest/specific version, using the pip3 command.

```
export PATH="$PATH:/home/ubuntu/.local/bin/"
```
> Add to path

### Install kOps: ###

```
curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

chmod +x kops-linux-amd64

sudo mv kops-linux-amd64 /usr/local/bin/kops
```