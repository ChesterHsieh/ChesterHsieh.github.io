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
#
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY4ODY4ODU0OSwtMTQ1MzgwNzAzMiwtNj
M2NjMwNTM2LC00MDk1MjY5OTUsMjA5NzE4Mzk1MywtMTY2NjE4
NDQ5OCwtNDkxMTc5MDk4LDExMzA1NDgwNzddfQ==
-->