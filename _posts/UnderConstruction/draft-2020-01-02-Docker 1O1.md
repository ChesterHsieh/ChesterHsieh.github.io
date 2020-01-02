---
layout:     post
title:      Docker 1o1
subtitle:   Note for Docker study guide
date:       2020-01-02
author:    Chester
header-img: 
catalog: true
tags:
    Project
---

# Installation
It should be good enough to follow instruction from [offcial web]([https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/)) for Ubuntu 18. 
Please step by step. 

Run the script below with shell script:
Don't forget to chmod +x xxx.sh
```
sudo apt-get update

sudo apt-get -y install \
  apt-transport-https \
  ca-certificates \
  curl \
  gnupg-agent \
  software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install -y docker-ce=5:18.09.5~3-0~ubuntu-bionic docker-ce-cli=5:18.09.5~3-0~ubuntu-bionic containerd.io

sudo usermod -a -G docker cloud_user
newgrp docker
```

## Supported storage drivers
Docker support graph driver, included:
`overlay2`, `aufs` and `btrfs`
Default driver is overlay2 for CentOS and Ubuntu.

Allow us write the data on internal container

## Permission
```
Unlike CentOS, the following install instruction give enoguh access for user on using docker command.?????
```


Not really. Don't forget the local machine is always using root account to control most of command. In the cloud server, other user need to be set for being in the dcoker group.

```
sudo usermod -a -G docker cloud_user
systemctl list-unit-files | grep docker
```
Help to find out if the docker service will start when we power on the system.

# Usage
## Run
```
docker run [option][image:TAG][COMMAND][ARG]```

```
```
docker run busybox echo hello world!
```
**Detach Mode**
Run on the background. Some severice just to run all the time. Yes, we can run machine leaning Saas on this mode.
***--name***
Give the name for the running container. (not image name)
***--restart on-failutre*** or***--restart always***  or ***--restart unless-stopped***
For the web service, we hope it'll always being running. 

***Publish port***
```-p 8080:70```

***--memory 500M --memory-reservation 256M nginx***
Memory to restrict to docker. 

## Login Driver
Framework for accessing log data from servvices and containers in Docker. Docker supports a variert of logging driver.


# Docker Swarm
It allows for easily building a distributed cluster where a container can be run across multiple available servers.

## Restore and backup
#### Create the Backup

On the manager:

```
sudo systemctl stop docker
sudo tar -zvcf backup.tar.gz -C /var/lib/docker/swarm
sudo systemctl start docker
```

#### Restore from Backup

On the manager:

```
sudo systemctl stop docker
sudo rm -rf /var/lib/docker/swarm/*
sudo tar -zxvf backup.tar.gz -C /var/lib/docker/swarm/
sudo systemctl start docker
docker node ls
```

##

# Backgound Knowledge
## Linux Namespace
Linux Namespace provide core-level enviroment isolation method. We can say, this method jail some process in to prison. 

This technology allows containers to operate independently and securely. 

***pid,net,ipc,mnt,uts,user namespaces*** are all unique.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzMxMjcxODc0LC03ODE1MDE4NDEsLTM2MT
I5NDE0NCwxNjc0NTExNDYwLC0xNDUzODA3MDMyLC02MzY2MzA1
MzYsLTQwOTUyNjk5NSwyMDk3MTgzOTUzLC0xNjY2MTg0NDk4LC
00OTExNzkwOTgsMTEzMDU0ODA3N119
-->