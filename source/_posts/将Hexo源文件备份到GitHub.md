---
title: 将Hexo源文件备份到GitHub
date: 2020-07-11 22:23:03
tags:
---

## 首次备份

在Hexo更目录下，初始话git仓库

```
git init
```

创建并切换分支‘hexo’

```
git checkout -b hexo
```

> 说明：默认master分支存放的是hexo构建的html文件

添加文件列表

```
git add -A
```

添加提交说明

git commit -m ‘首次备份Hexo源文件’

设置远程仓库映射

```
git remote add origin git@github.com:myenglandgirl/myenglandgirl.github.io
```

提交

```
git push -u origin hexo
``` 

## 之后备份

```
git add -A
git commit -m '备份Hexo源文件'
git push origin hexo
或git push
```

