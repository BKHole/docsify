# 组件-多级列表（tree）

## 为什么要做这个组件

当然是业务需要啦，以及造个轮子方便以后使用。前端开发中，树状显示数据是一种很常见的需求，常见的UI库，如antd、element中都有相应的组件。项目使用的是原生小程序开发，官方并没有提供相应的组件，却提供了另一种解决方式，自定义组件。

## 核心思路

基本的树状结构实现的核心思路都是通过递归。小程序中也不例外，在自定义组件中调用组件本身。

## 组件交互事件

一般展开内容可能会涉及点击交互，这里使用组件事件传递，

``` code
/*
* param1: 自定义事件名 string
* param2: 传递数据 object
* param3: 事件触发机制配置 object
*/
this.triggerEvent('customevent', {}, { bubbles: true, composed: true })
```

## 效果图

![tree-view](https://raw.githubusercontent.com/BKHole/resource/master/tree-component/tree.gif)

## 实际运用

![tree-view](https://raw.githubusercontent.com/BKHole/resource/master/tree-component/tree-2.gif)

### 补充

展示数据太多可以滑动时，可分级请求数据展示，避免页面卡死。无限滚动列表视图可以使用官方组件recycle-view，提升页面渲染

## 具体实现

* [小程序代码片段](https://developers.weixin.qq.com/s/CBCMWkmf7Gcb)
* [github地址](https://github.com/BKHole/tree-component)

## 参考

* [vue树形图](https://cn.vuejs.org/v2/examples/tree-view.html)
