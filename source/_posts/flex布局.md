---
title: flex布局
date: 2022-07-08 10:42:53
tags: css
categories: 技术
---

# 用于父元素的属性
1. `justify-content` 主轴元素排列方式
> 1. center
> 2. flex-start
> 3. flex-end
> 4. space-between
> 5. space-around
> 6. space-evenly **间隔均匀分布**

1. `align-items` 交叉轴的元素排列方式
2. `flex-direction` 排列方式
3. `flex-wrap` 元素是否可换行

# 用于子元素的属性
1. `flex-grow` 占据盒子剩余空间
   > flex-grow: 1
2. `flex-shrink` 不换行是否可压缩
   > flex-shrink: 0
3. `flex-basis` 盒子初始值
4. `flex` 前三项的缩写
   > flex-grow: 1 等价于 flex: 1
5. `align-self` 覆盖父元素指定交叉轴的属性align-items
6. `order` 指定元素的排列顺序；**order**越大排序越后
7. `z-order` 元素重叠时，值较大的会在上层显示
