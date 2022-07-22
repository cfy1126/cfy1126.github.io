---
title: react后台管理项目五
date: 2022-07-21 19:32:47
tags: react
categories: 技术
---

`ref`操作使用：

```javascript
  constructor(props) {
    super(props)
    // 定义ref对象
    this.numberRef = React.createRef()
  }

  // 指定元素
  <select ref={this.numberRef}>
    <option value="1">1</option>
    <option value="2">2</option>
    <option value="3">3</option>
  </select>

  // 操作dom
  increment = () => {
    const number = this.numberRef.current.value * 1
    this.props.increment(number)
  }
```

`return`：返回结果如果是一个对象需要用括号`({})`

`react-redux插件`：解决react代码和redux代码耦合性太高的问题

`redux`
![redux原理](../img/react后台管理项目/redux原理.png)

`react-redux`
![react-redux原理](../img/react后台管理项目/redux原理.png)

`redux-thunk`
```javascript
/**
 * redux最核心的管理对象
 * redux默认不支持异步
 */

import { createStore, applyMiddleware } from 'redux'
import reducer from './reducer'
import thunk from 'redux-thunk' //用来实现redux异步的redux中间件插件
// redux调试工具
import { composeWithDevTools } from 'redux-devtools-extension'

export default createStore(reducer, composeWithDevTools(applyMiddleware(thunk))) //创建store对象内部会第一次调用reducer

// 异步增加的action
export const incrementAsync = (number) => {
  return (dispatch) => {
    // 执行异步（定时器，promise）
    setTimeout(() => {
      dispatch(increment(number))
    }, 1000)
  }
}
```