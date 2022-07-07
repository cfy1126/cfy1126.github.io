---
title: 前端下载图片
date: 2022-07-06 22:39:56
tags: Javascript
---

> 前端下载api返回为图片格式

```javascript
const downloadDocument = async () => {
  const res = await http.get(`${path}?user_id=caofy@inhand.com.cn`, {
    responseType: 'blob',
  })
  downFile(res.data, 'download')
}

const downFile = (data, name) => {
  if (!data) {
    alert('数据错误！')
    return
  }
  let BLOB = new Blob([data])
  let url = window.URL.createObjectURL(BLOB)
  let link = document.createElement('a')
  link.style.display = 'none'
  link.href = url
  link.setAttribute('download', name)
  document.body.appendChild(link)
  link.click()
}
```
