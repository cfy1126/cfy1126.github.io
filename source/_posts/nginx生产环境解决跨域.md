---
title: nginx生产环境解决跨域
date: 2022-07-25 17:56:27
tags: nginx
categories: 技术
---
# 运行nginx
![](../img/nginx操作/i.png)
- 路径不能有中文

# 配置转发
![](../img/nginx操作/o.png)

# 生产环境
`打包`：*npm run build*

`查看`：*npm install -g serve*

`启动`：*serve build*

# 无跨域问题
- 打包后的前台代码全部复制到后台代码中的`public`文件夹中，然后启动后端代码，直接可以访问打包后的前台代码，前后台使用同一个端口，故无跨域问题。

