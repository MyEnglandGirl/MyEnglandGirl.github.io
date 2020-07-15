---
title: hexo模板JS库优化，加快网站访问速度
date: 2020-07-15 12:14:58
tags: Hexo
---

目前使用的 landscape 模板

找到` themes/landscape/layout/_partial/after-footer.ejs `这个文件

```
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>  
```

替换为下面代码

```
<script src="https://apps.bdimg.com/libs/jquery/2.0.3/jquery.min.js"></script>
```

找到` themes/landscape/layout/_partial/head.ejs `这个文件

将下面代码删除

```
<link href="http://fonts.googleapis.com/css?family=Source+Code+Pro" rel="stylesheet" type="text/css
```

