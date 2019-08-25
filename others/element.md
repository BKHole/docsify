# 如何让Element UI的Message消息提示每次只弹出一个

## 解决方案

过对Message分析可以得知：Element UI在调用Message组件时会在HTML中插入以下代码，所以我们可以通过document.getElementsByClassName('el-message').length > 0来判断当前页面是否已存在Message。

## 实现代码

``` code
import ElementUI, { Message } from 'element-ui'
// ... 

Vue.use(ElementUI)
// 命名根据需要，DonMessage只是在文章中使用
Vue.prototype.$message = new DonMessage()

// ...

// 为了实现Class的私有属性
const showMessage = Symbol('showMessage')
/** 
 *  重写ElementUI的Message
 *  single默认值true，因为项目需求，默认只弹出一个，可以根据实际需要设置
 */
class DonMessage {
  success (options, single = true) {
    this[showMessage]('success', options, single)
  }
  warning (options, single = true) {
    this[showMessage]('warning', options, single)
  }
  info (options, single = true) {
    this[showMessage]('info', options, single)
  }
  error (options, single = true) {
    this[showMessage]('error', options, single)
  }

  [showMessage] (type, options, single) {
    if (single) {
      // 判断是否已存在Message
      if (document.getElementsByClassName('el-message').length === 0) {
        Message[type](options)
      }
    } else {
      Message[type](options)
    }
  }
}
```
