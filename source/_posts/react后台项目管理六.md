---
title: react后台项目管理六
date: 2022-07-29 21:47:38
tags: react
categories: 技术
---

# react-router@4.x

- 返回组件跳转`<Redirect to="/"></Redirect>`

- 标签跳转`<Link to="/" ></Link>`

- 编程式跳转`this.props.history.replace('/login')`

# access_token 和 refresh_token

- 源码

  - 前端[react 代码](https://github.com/scalablescripts/react-auth-refresh)
  - 后端[node 代码](https://github.com/scalablescripts/node-auth-refresh)

- 视频
  - [前端](https://www.youtube.com/watch?v=VJLSaq1Ll0U&t=1s)
  - [后端](https://www.youtube.com/watch?v=cvRCVMFTbBM&list=PLlameCF3cMEtB7i9d7VmL2PMjhXOJXArA&index=1&t=275s)

# 不要用 http 请求 https 的 api

# 对象遍历

- **for...in..**

  ```javascript
  for (key in test) {
    console.log(key)
    console.log(text(key))
  }
  ```

- **forEach**
  ```javascript
  var obj = { 0: 'a', 1: 'b', 2: 'c' }
  Object.keys(obj).forEach(function(key){
     console.log(key,obj[key]);
  });
  ```

  # undefind
  - 变量未初始化(const,let)
  - 对象不存则的属性
  - 数组不存在的项

## 解决
`检查属性是否存在`
- *obj.prop！== undefined* 直接与undefined进行比较
- *typeof obj.prop！=='undefined'* 验证属性值类型
- *obj.hasOwnProperty（'prop'）* 验证对象是否具有自己的属性
- *'prop' in obj* 验证对象是否具有自己的属性或继承属性

`解构访问对象属性`
```javascript
// 三元运算符号
const object = { };
const prop = 'prop' in object ? object.prop : 'default';
prop; // => 'default'

// 解构使用默认值
const object = {  };
const { prop = 'default' } = object;
prop; // => 'default'
```
`函数参数使用默认值`
```javascript
function multiply(a, b = 2) {
  a; // => 5
  b; // => 2
  return a * b;
}
multiply(5);            // => 10
multiply(5, undefined); // => 10  
```