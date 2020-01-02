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
Docker support graphDriver, included:
`overlay2`, `aufs` and `btrfs`
Default driver is overlay2,

Allow us write the data i

## Permission
```
Unlike CentOS, the following install instruction give enoguh access for user on using docker command.?????
```


Not really. Don't forget the local machine is always using root account to control most of command. In the cloud server, other user need to be set for being in the dcoker group.

``````
sudo usermod -a -G docker cloud_user
``````
systemctl list-unit-files | grep docker
```
Help to find out if the docker service will start when we power on the system.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNjI4MTkyMzYsMjA5NzE4Mzk1MywtMT
Y2NjE4NDQ5OCwtNDkxMTc5MDk4LDExMzA1NDgwNzddfQ==
-->