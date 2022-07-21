---
title: react后台管理项目四
date: 2022-07-19 18:16:03
tags: react
---

`简单空格`：**&nbsp**

`请求`：**收集数据-->发送请求-->响应处理-->提示用户**

`关于改变类组件状态`：

- 替换原数组使用*this.setState({roles})* **简洁**
- 组件基于原本的状态去修改
  ```javascript
  this.setState(state => ({roles: [...state.roles,role]})
  ```
  `react富文本插件`：_react-draft-wysiwyg_

`收集数据`

- **form**
- **ref**(父组件收集子组件的数据）

`前台分页`：一次性查出所有的数据

`组件传值`：_不修改组件传入的数据状态，只修改自己的数据状态_

```javascript
this.auth = React.createRef()
// 得到最新的menus
const menus = this.auth.current.getMenus()
<AuthForm role={role} ref={this.auth} />

/**
 * 为父组件提供最新menus数据
 * @returns
 */
getMenus = () => this.state.checkedKeys
```

`绑定事件`：绑定事件传递参数的写法 **()=> this.deleteUser(user)**

`undefind`：防止出现undefind，写成三元运算符的形似

`输入框`：取消输入的时候应该重置输入框

`强制转换成布尔值`：
```javascript
return !!item.children.find((child) => menus.indexOf(child.key) !== -1)
```
*状态===属性 行为===函数*