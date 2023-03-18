# 使用sendBeacon发送请求

  使用此api发送异步请求，跳出页面控制，交由浏览器管理

## 问题出现
  在统计数据和发送页面诊断报告，页面卸载，请求发送中断

## 介绍
  navigator.sendBeacon() 方法可用于通过 HTTP POST 将少量数据异步传输到 Web 服务器。

  它主要用于将统计数据发送到 Web 服务器，同时避免了用传统技术（如：XMLHttpRequest）发送分析数据的一些问题。

  一种AJAX请求方式


## 使用
  ``` javascript
  navigator.sendBeacon(url,data)
  ```

## 与XMLHttpRequest 的区别
  ``` javascript 
  // XMLHttpRequest 
    let xml = new XMLHttpRequest ()
    xml.open(method,url)
    xml.send()
  ```
  
## 注意
数据是通过 HTTP POST 请求发送的。
