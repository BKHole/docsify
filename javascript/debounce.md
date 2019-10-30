# 前端性能相关：防抖、节流

### 防抖（debounce）

作用是在短时间内多次触发同一个函数，只执行最后一次，或者只在开始时执行。

``` code
// debounce 函数接受一个函数和延迟执行的时间作为参数
function debounce(fn, delay){
    // 维护一个 timer
    let timer = null;
    
    return function() {
        // 获取函数的作用域和变量
        let context = this;
        let args = arguments;
        
        timer && clearTimeout(timer);
        timer = setTimeout(function(){
            fn.apply(context, args);
        }, delay)
    }
}
```

### 节流（throttle）

节流是在一段时间内只允许函数执行一次。

``` code
function throttle(func, delay){
    let prev = Date.now();
    return function(){
        let context = this;
        let args = arguments;
        let now = Date.now();
        if(now-prev>=delay){
            func.apply(context,args);
            prev = Date.now();
        }
    }
}
```
