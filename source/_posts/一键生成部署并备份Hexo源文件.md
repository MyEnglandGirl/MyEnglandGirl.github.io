---
title: 一键生成部署并备份Hexo源文件
date: 2020-07-12 13:32:15
tags: Hexo
---

默认安装Hexo的时候就已经给我们提供几个命令

可以打开`package.json`查看详情,如下：

```
  "scripts": {
    "build": "hexo generate",
    "clean": "hexo clean",
    "deploy": "hexo deploy",
    "server": "hexo server"
  },
```

我们可以用`npm run build`运行

关于Hexo常用语法，见：

 [https://myenglandgirl.github.io/2020/07/12/%E4%BD%BF%E7%94%A8hexo%E6%90%AD%E5%BB%BAgithub%E5%8D%9A%E5%AE%A2/](https://myenglandgirl.github.io/2020/07/12/使用hexo搭建github博客/) 

关于备份Hexo源文件到github，见：

 [https://myenglandgirl.github.io/2020/07/11/%E5%B0%86Hexo%E6%BA%90%E6%96%87%E4%BB%B6%E5%A4%87%E4%BB%BD%E5%88%B0GitHub/](https://myenglandgirl.github.io/2020/07/11/将Hexo源文件备份到GitHub/) 

我们可以修改命令，是这个一键生成

修改build命令如下

```
  "scripts": {
    "build": "hexo clean && hexo g -d && git add -A && git commit -m '备份hexo源文件' && git pull && git push",
    "clean": "hexo clean",
    "deploy": "hexo deploy",
    "server": "hexo server"
  },
```

默认先清除缓存文件和已生成的静态文件

然后生成静态文件并部署都GitHub	

最后提交Hexo源文件，同步到博客的hexo分支