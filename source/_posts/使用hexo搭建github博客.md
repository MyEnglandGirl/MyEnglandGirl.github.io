---
title: 使用hexo搭建github博客
date: 2020-07-12 12:51:18
tags:Hexo
---

### 创建github仓库

首先打开github，点击New repository，创建一个新仓库，仓库名必须要遵守格式：账户名.github.io，不然接下来会有很多麻烦。并且需要勾选Initialize this repository with a README

> 例如： [MyEnglandGirl.github.io](https://github.com/MyEnglandGirl/MyEnglandGirl.github.io) 

### 安装hexo

自行检查是否安装node和git

全局安装hexo

```
npm install hexo -g
```

检查hexo是否安装成功

```
hexo -v
```

创建一个文件夹，在文件夹根目录下初始化文件夹

```
hexo init
```

安装需要的组件

```·
npm i 
```

执行命令

```
$ hexo g #generate 生成静态文件
$ hexo s #server 启动服务器。默认情况下，访问网址为： [http://localhost:4000/]
```

### 链接hexo和git

 设置你的用户名称与邮件地址，如果是第一次使用git的话 

```
$ git config --global user.name "name"
$ git config --global user.email name@example.com
```

 使用ssh-keygen生成私钥和公钥 

```
$ ssh-keygen -t rsa
```

 登录Github，点击头像下的settings，添加ssh,新建一个new ssh key，将id_rsa.pub文件里的内容复制上去。 

测试添加ssh是否成功。如果看到Hi后面是你的用户名，就说明成功了 

```
ssh -T git@github.com
```

 配置Deployment，在hexo初始化的文件夹中，找到_config.yml文件，修改repo值（在末尾），repo值是github项目里的ssh。 

```
deploy:
  type: 'git'
  repository: git@github.com:MyEnglandGirl/MyEnglandGirl.github.io.git
  branch: master
```

> 注意：冒号后面有个空格

修改配置文件 _config.yml文件后 ，需要重新部署一下，否则不生效

```
hexo deploy
```

如果还不生效，需要clean一下

```
hexo clean
```

使用工具将hexo博客部署到github

```
$ npm install hexo-deployer-git --save
```

创建文章(使用默认模板，可以根据需要自行修改)

```
$ hexo new [layout] <title>  #新建文章
<!--例如-->
# [layout] : 模板名，可省略，也可自定义模板
$ hexo new  hello
```

使用编辑器编辑好文章，接着就可以上传到github上，可以通过设置的域名进行访问

默认文章目录在` ‘/source/_posts’ `下

部署

```
 hexo d -g
```

 生成以及部署了。在打开你的博客主页就可以看到你创建的文章了。 

[MyEnglandGirl.github.io](https://github.com/MyEnglandGirl/MyEnglandGirl.github.io) 

### 常用命令

```
hexo g #generate 生成静态文件
hexo s #server 启动服务器。在本地预览效果，默认情况下，访问网址为： http://localhost:4000/
hexo d #deploy 部署网站同步到github。部署网站前，需要预先生成静态文件
hexo clean #clean 清除缓存文件 (db.json) 和已生成的静态文件 (public)。
```

### Hexo文件目录结构

```
├── .deploy          #部署文件夹
├── public           #html源码，hexo g生成
├── scaffolds        #模板
├── scripts          #扩展脚本
├── source           #文章源码
|   ├── _drafts      #草稿
|   └── _posts       #文章
├── themes           #主题
|   ├── next         #NexT主题
├── _config.yml      #博客配置
└── package.json     #应用程序数据
```

