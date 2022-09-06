---
layout: git
title: denied
date: 2022-09-06 22:35:20
tags: git
---





## 问题描述

 git clone时出现Permission denied (publickey) 



## 解决方案

1. 启动Git Bash 

    右键，在弹出的快捷菜单中，选择 **git bash here**： 

2. 检查是否生成SSH KEY

   ```bash
   # 切换到.ssh目录
   > cd ~/.ssh
   # 查看当前目录下所有文件
   > ls
   ```

   检查.ssh目录下是否有 **xxx_rsa.pub** 文件 ，没有需要生成，有直接跳转到第五步。

3. 生成SSH KEY

   ```
   > ssh-keygen -t rsa -C "你的邮箱地址"
   ```

   按照提示输入文件名称和密码

4. 添加SSH KEY 到SSH-AGENT

   ```
   ssh-add ~/.ssh/id_rsa
   ```

5. 添加SSH KEY到GitHub

   点击右上角用户头像 --> Settings 菜单项 --> SSH and GPG keys 菜单项 --> New SSH key 按钮

   使用less命令打开id_rsa.pub

   ```
   less id_rsa.pub
   ```

   复制文件内容，粘贴到github内，title随便填。

   

   