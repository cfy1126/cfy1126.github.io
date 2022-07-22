---
title: react中使用样式预处理less
date: 2022-07-13 18:00:10
tags: react
categories: 技术
---

`安装craco`: yarn add @craco/craco

`安装craco-less`：yarn add craco-less

创建`craco.config.js`：
```javascript
const CracoLessPlugin = require('craco-less');

module.exports = {
  plugins: [
    {
      plugin: CracoLessPlugin,
      options: {
        lessLoaderOptions: {
          lessOptions: {
            modifyVars: { '@primary-color': '#1DA57A' },
            javascriptEnabled: true,
          },
        },
      },
    },
  ],
};
```

`antd`自定义主题
![](../img/react使用less预处理器/i.png)
