---
title: My Install Scripts for WSL
category: Windows Subsystem for Linux
order: 1
---
# My Install Scripts for WSL

Here are some example scripts that I use to setup my Windows Subsystem for Linux (WSL) environment.

## Azure Command Line

``` bash
echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ wheezy main" | sudo tee /etc/apt/sources.list.d/azure-cli.list
sudo apt-get update
sudo apt-get upgrade
sudo apt-key adv --keyserver packages.microsoft.com --recv-keys 417A0893
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python
sudo apt-get install azure-cli
```

## .NET Core

``` bash
sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 417A0893
sudo apt-get update
sudo apt-get install dotnet-dev-1.0.4
```

## Node / NPM

``` bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## KubeCtl

``` bash
az login
sudo az acs kubernetes install-cli
```

## Docker (just for CLI)

``` bash
wget -qO- https://get.docker.com/ | sh
sudo usermod -aG docker jwendl
```

## Docker Compose

``` bash
wget https://github.com/docker/compose/releases/download/1.14.0/docker-compose-`uname -s`-`uname -m`
sudo cp docker-compose-Linux-x86_64 /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## Bash Aliases (put inside .bash_aliases)

``` bash
alias docker="docker -H localhost:2375"
alias docker-compose="docker-compose -H localhost:2375"
```

## Helm

``` bash
wget https://storage.googleapis.com/kubernetes-helm/helm-v2.5.0-linux-amd64.tar.gz
tar -zxvf helm-v2.5.0-linux-amd64.tar.gz
sudo mv linux-amd64/helm /usr/local/bin
helm init
```

## Draft

``` bash
wget https://azuredraft.blob.core.windows.net/draft/draft-canary-linux-amd64.tar.gz
tar -zxvf draft-canary-linux-amd64.tar.gz
sudo mv linux-amd64/draft /usr/local/bin
draft init
```

## Draft Example App

``` bash
git clone https://github.com/Azure/draft.git
cd draft/examples/dotnetcore
draft create
draft up
```

## Install Terraform

``` bash
wget https://releases.hashicorp.com/terraform/0.10.8/terraform_0.10.8_linux_amd64.zip?_ga=2.122096331.1762544404.1509907251-1265081840.1498085730 -O terraform.zip
unzip terraform.zip
chmod 700 terraform
sudo mv terraform /usr/local/bin/terraform
```

## Set Terminal Colors

> Go to [GitHub Repo](https://github.com/Microsoft/Console/tree/master/tools/ColorTool) and run through steps

``` cmd
colortool solarized_dark
colortool -b solarized_dark
```
