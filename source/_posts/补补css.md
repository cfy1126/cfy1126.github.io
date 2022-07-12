---
title: 补补css
date: 2022-07-12 08:25:58
tags: css
---

# 外边距塌陷(margin collapsing)

1. 只会发生在垂直方向上，不会发生在水平方向
![header]( img/../../img/margin%20collapsing/i.png)

2. 父元素和子元素没有内容
> 父元素包裹子元素，且在同一方向上没有padding和border
>`解决办法`：在同一方向上设置padding和border

![header](img/../../img/margin%20collapsing/o.png)

1. 空元素
![header](img/../../img/margin%20collapsing/p.png)

# 内联元素和行内块元素
`内联元素`：宽高以及到顶部和底部的边距都不可以进行设置
`行内块元素`：内容在一行，其它设置和块元素相同
