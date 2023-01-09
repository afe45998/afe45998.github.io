---
title: 搭建Hexo博客
tags: [hexo]
categories: 教程
---
# 1. 安装Node.js
· URL: www.nodejs.org

# 2. 安装hexo
· 以管理员身份运行Git Bash

· 切换镜像源
```
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
```
· 安装hexo
```
$ cnpm install -g hexo-cli
```
<!--more-->

# 3. 关于SSH
· Open Git Bash<br/>
· Generating a new SSH key and adding it to the ssh-agent
```
$ ssh-keygen -t ed25519 -C "your_email@example.com"

OR

$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
· Adding your SSH key to the ssh-agent<br/>
1) Ensure the ssh-agent is running
```
# start the ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid 59566
```
2) Add your SSH private key to the ssh-agent
```
$ ssh-add ~/.ssh/id_ed25519
```
3) Add the SSH key to your account on GitHub<br/>

· Adding a new SSH key to your account
1) Copy the SSH public key to your clipboard
```
$ clip < ~/.ssh/id_ed25519.pub
  # Copies the contents of the id_ed25519.pub file to your clipboard
```