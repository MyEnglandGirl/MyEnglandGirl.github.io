---
title: 从github导出备份的hexo源文件
date: 2020-07-15 10:05:48
tags: Hexo
---

安装node，git，hexo

将备份的hexo分支导出到本地

```
git clone url -b 分支名字 folder_name
git clone https://github.com/MyEnglandGirl/MyEnglandGirl.github.io.git -b hexo blog
```

在导出的文件夹下面，安装需要的依赖

```
npm i
```

注意：

默认首次安装git，需要初始化邮箱和用户名

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

hexo首次部署需要生成公钥和私钥

使用ssh-keygen生成私钥和公钥 

```
$ ssh-keygen -t rsa
```

登录Github，点击头像下的settings，在左侧店家`SSH and GPG keys`

添加ssh,新建一个new ssh key，将id_rsa.pub文件里的内容复制上去。

测试添加ssh是否成功。如果看到Hi后面是你的用户名，就说明成功了。

```
ssh -T git@github.com
```

新建一篇文章

```
hexo new 备份测试
```

生成部署并备份到github（之前的文章已经说过重写了打包命令，需要自己修改）

```
npm run build
```



