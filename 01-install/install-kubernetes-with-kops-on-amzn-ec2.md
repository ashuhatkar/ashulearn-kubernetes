## Kubernetes setup using Kubernetes Operations (kOps) on Amazon EC2 ##

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

> The command prints out the line describing the relevant repository and this is piped to <mark>sudo tee</mark> as a way of writing to <mark>/etc/apt/sources.list.d/kubernetes.list</mark>. Replace the <mark>apt</mark> repository definition so that <mark>apt</mark> points to the new repository instead of the Google-hosted repository. Make sure to replace the Kubernetes minor version in the command below with the minor version you're currently using.

```
echo "deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

* Install the Python, AWS CLI, Kubectl workloads, using the following commands:

> The command <mark>sudo get-apt update</mark> downloads package information from all configured sources.

```
sudo apt-get update
sudo apt-get install -y python3-pip python3-venv kubectl
```

> Verify the installation
```
which python3
pip3 --version
kubectl version
```

> The command install AWS CLI latest/specific version, using the pip3 command.

- For an externally managed environment, create and activate a virtual environment using:
```
python3 -m venv .venv
source .venv/bin/activate
```

- For the latest version of the AWS CLI using pip3
```
pip3 install awscli --upgrade
```

- For the specific version of the AWS CLI using pip3
```
pip3 install awscli<1.6.312 --upgrade
```

(Ref: https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)

> The command downloads, verifies and installs AWS CLI latest/specific version, using the curl command.

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install
```

> The command update AWS CLI latest/specific version, using the curl command.

```
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
sudo apt install unzip
unzip awscliv2.zip
sudo ./aws/install --bin-dir /usr/local/bin --install-dir /usr/local/aws-cli --update
```

> The command installs AWS CLI latest version, using the curl command.

```
curl -o awscliv2.sig https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip.sig
```

> The command installs AWS CLI specific version, using the curl command.

```
curl -o awscliv2.sig https://awscli.amazonaws.com/awscli-exe-linux-x86_64-2.0.30.zip.sig
```

> Verify that the AWS CLI install correctly
```
which aws
aws --version
```

> Set the path environment for the current session.

```
export PATH="$PATH:/home/ubuntu/.local/bin/"
```

### Install kOps: ###

```
curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64

chmod +x kops-linux-amd64

sudo mv kops-linux-amd64 /usr/local/bin/kops
```

### Configure the AWS CLI ###

```
aws configure
AWS Access Key ID [None]: accesskey
AWS Secret Access Key [None]: secretkey
Default region name [None]: us-east-2
Default output format [None]:
```
```
aws configure [--profile profile-name]
```

> If the command is run with no arguments, you will be prompted for configuration values such as your AWS Access Key id and your AWS Secret Access Key. You can configure a named profile using the --profile argument. If your config file does not exist (default location is \~/.aws/config), the AWS CLI will create it for you. The values you provide will be written to the shared credentials file (~/.aws/credentials)