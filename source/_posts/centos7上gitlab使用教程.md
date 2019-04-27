---
title: centos 7 上gitlab使用教程
tags: git
categories: 工具
img: https://res.cloudinary.com/lumiazdk/image/upload/v1554635036/q7kz9phy9gkv5u6idn6v.png
---
## 1安装gitlab
 ``` shell
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash 
sudo yum install gitlab-ce 
```

## 修改配置
``` shell
vim /etc/gitlab/gitlab.rb
 ```
### 常用gitlab命令
## 启动
``` shell
sudo gitlab-ctl start
 ```
## 停止
``` shell
 sudo gitlab-ctl stop
 ```
## 重启
```shell
 sudo gitlab-ctl restart
 ```
## 重置配置
```shell
 sudo gitlab-ctl reconfigure 
```
## 2安装 gitlab-runner
## 添加repository
```shell
 curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-ci-multi-runner/script.rpm.sh | sudo bash
 ```
## 安装包
```shell
 yum install gitlab-runner
 ```
## 注册runner
```shell
 sudo gitlab-runner register
 ```
> 执行上述命令之后，之后的流程如下：
>第一处红线：输入部署完成的gitlab地址比如http://111.111.111.111:8080/
>第二处红线: 输入token，token的值可以在登录gitlab之后，下图所示位置找到，先点击右上方Admin Settings，再找到左侧列表的runners

![](https://res.cloudinary.com/lumiazdk/image/upload/v1554635068/hmpoapgta6jrvljd25md.png)
![](https://res.cloudinary.com/lumiazdk/image/upload/v1554635084/hjswdrq7ajbjod0ssuw5.png)

>选executor时不了解docker的可以选shell，根据提示输入账户密码即可注册成功
>最后gitlab中会出现runner

![](https://res.cloudinary.com/lumiazdk/image/upload/v1554635100/le8faa2sg5nrgci7gmvg.png)

>配置成功！