## Kubernetes setup using Kubernetes Operations kOps on Amazon EC2 ##

### Create an EC2 instance or you can make use of your personal infrastructure. ###

Pre-requisites:

1. AWS subscription
2. AWS command-line interface (CLI)
3. Python3
4. Kube command-line interface (Kubectl)

### Install dependencies: ###

> Install the Apt repository signing keys, using the following command:
> The command downloads a gpg signature from https://packages.cloud.google.com/apt/doc/apt-key.gpg which is then piped to sudo apt-key add - (the - mean "read from standard input") which adds the key to the list of known apt keys.
>
```
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```
> The command prints out the line describing the relevant repository and this is piped to sudo tee as a way of writing to /etc/apt/sources.list.d/kubernetes.list.
>
```
echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
```
>

Here are few resources and steps to get you started:

You'll learn how to:

1. Create a kubernetes cluster
2. Deploy an app:
3. Explorer your app:

