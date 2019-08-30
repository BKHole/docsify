# js循环及中断

## forEach

forEach循环中return、retrun true、return false只能跳出本次循环，不能跳出整个循环。

##  Array.erery()

``` code
var a = [1, 2, 3, 4].erery(function(item, i) {
    return item < 3;
});
```

return false跳出整个循环，return true跳出本次循环，继续循环；

##  Array.some()

``` code
var a = [1, 2, 3, 4].some(function(item, i) {
    return item < 3;
});
```

return true跳出整个循环，return false跳出本次循环，继续循环; 

## for

break用于跳出整个循环(当前for)，continue用于跳出本次循环；
如果是多层嵌套的循环，要跳出所有循环，则需给最外层循环命名；

``` code
f:for(var i = 0; i < 3; i++) {
    for(var j = 0; j < 3; j++) {
        if (i === 0 && j === 0) {
          break f;
        }  
    console.log(i, j);
  }
}
```
