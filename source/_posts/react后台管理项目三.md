---
title: react后台管理项目三
date: 2022-07-15 22:53:46
tags: react
categories: 技术
---

`引入文件`：

- 只有**js**和**jsx**可以省略后缀
- export default 暴露导入文件可以写任意名字
- export default 暴露导入时不用写中括号
- export 统一导出导入时需要写中括号

`路由`：为谁设置二级路由，就在哪里配置

`bug`:

- 功能性 bug(报错）
- 异常 bug(不报错）

## 2. jsonp 解决 ajax 跨域的原理

    1). jsonp只能解决GET类型的ajax请求跨域问题
    2). jsonp请求不是ajax请求, 而是一般的get请求
    3). 基本原理
        浏览器端:
            动态生成<script>来请求后台接口(src就是接口的url)
            定义好用于接收响应数据的函数(fn), 并将函数名通过请求参数提交给后台(如: callback=fn)
        服务器端:
            接收到请求处理产生结果数据后, 返回一个函数调用的js代码, 并将结果数据作为实参传入函数调用
        浏览器端:
            收到响应自动执行函数调用的js代码, 也就执行了提前定义好的回调函数, 并得到了需要的结果数据

`find`:

- 找到一个匹配的元素就返回这个元素，并且不再向下进行

`类组件生命周期`：

> 组件卸载之前清除定时器

- _挂载阶段_：constructor--->render--->componentDidMount
- _更新阶段_：render--->componentDidUpdate
- _卸载阶段_：componentWillUnmount

`css`:

- _伪元素_
- _透明_
- _移动_
- _定位_

```css
.header-bottom-left {
  width: 25%;
  text-align: center;
  font-size: 20px;
  position: relative;
  &::after {
    content: '';
    right: 50%;
    top: 100%;
    transform: translateX(50%);
    position: absolute;
    border-top: 20px solid #fff;
    border-bottom: 20px solid transparent;
    border-left: 20px solid transparent;
    border-right: 20px solid transparent;
  }
}
```

`工具类`：

**格式化 date 对象**：

```javascript
export function formateDate(time) {
  if (!time) return ''
  let date = new Date(time)
  return (
    date.getFullYear() +
    '-' +
    (date.getMonth() + 1) +
    '-' +
    date.getDate() +
    ' ' +
    date.getHours() +
    ':' +
    date.getMinutes() +
    ':' +
    date.getSeconds()
  )
}
```

`组件`：

- 按钮封装成`a`标签效果

  ```javascript
  export default function LinkButton(props) {
    return <button {...props} className="link-button"></button>
  }

  .link-button{
  background-color: transparent;
  border: none;
  outline: none;
  color: #1da57a;
  cursor: pointer;
  }
  ```

  
