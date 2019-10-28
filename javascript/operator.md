# 算术运算符

算术运算符以数值（字面量或变量）作为其操作数，并返回一个单个数值。标准算术运算符是加法（+），减法（ - ），乘法（*）和除法（/）。

### 加法(+)

``` code
// Number + Number -> 数字相加
1 + 2 // 3

// Boolean + Number -> 数字相加
true + 1 // 2

// Boolean + Boolean -> 数字相加
false + false // 0

// Number + String -> 字符串连接
5 + "foo" // "5foo"

// String + Boolean -> 字符串连接
"foo" + false // "foofalse"

// String + String -> 字符串连接
"foo" + "bar" // "foobar"
```

### 减法 (-)

``` code
5 - 3 // 2
3 - 5 // -2
"foo" - 3 // NaN
```

### 除法 (/)

``` code
1 / 2      // 在 JavaScript 中返回 0.5
1 / 2      // 在 Java 中返回 0
// （不需要数字是明确的浮点数）

1.0 / 2.0  // 在 JavaScript 或 Java 中都返回 0.5

2.0 / 0    // 在 JavaScript 中返回 Infinity
2.0 / 0.0  // 同样返回 Infinity 
2.0 / -0.0 // 在 JavaScript 中返回 -Infinity
```

### 乘法 (*)

``` code
2 * 2 // 4
-2 * 2 // -4
Infinity * 0 // NaN
Infinity * Infinity // Infinity
"foo" * 2 // NaN
```

### 求余 (%)

``` code
12 % 5 // 2
-1 % 2 // -1
NaN % 2 // NaN
1 % 2 // 1
2 % 3 // 2
-4 % 2 // -0
5.5 % 2 // 1.5
```

### 幂 (**)

``` code
2 ** 3 // 8
3 ** 2 // 9
3 ** 2.5 // 15.588457268119896
10 ** -1 // 0.1
NaN ** 2 // NaN

2 ** 3 ** 2 // 512
2 ** (3 ** 2) // 512
(2 ** 3) ** 2 // 64
-(2 ** 2) // -4
(-2) ** 2 // 4
```

### 递增 (++)

``` code
// 后置 
var x = 3;
y = x++; 
// y = 3, x = 4

// 前置
var a = 2;
b = ++a; 
// a = 3, b = 3
```

### 递减 (--)

``` code
// 后置 
var x = 3;
y = x--; // y = 3, x = 2

// 前置
var a = 2;
b = --a; // a = 1, b = 1
```

### 一元负号 (-)

``` code
var x = 3;
y = -x; // y = -3, x = 3
-'2'; // -2
-'abd' // NaN
```

### 一元正号 (+)

一元正号运算符位于其操作数前面，计算其操作数的数值，如果操作数不是一个数值，会尝试将其转换成一个数值。 尽管一元负号也能转换非数值类型，但是一元正号是转换其他对象到数值的最快方法，也是最推荐的做法，因为它不会对数值执行任何多余操作。它可以将字符串转换成整数和浮点数形式，也可以转换非字符串值 true，false 和 null。小数和十六进制格式字符串也可以转换成数值。负数形式字符串也可以转换成数值（对于十六进制不适用）。如果它不能解析一个值，则计算结果为 NaN。

``` code
+3     // 3
+"3"   // 3
+true  // 1
+false // 0
+null  // 0
+function(val){ return val;} //NaN
```