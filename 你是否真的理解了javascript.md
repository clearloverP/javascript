英文原文地址：http://dmitry.baranovskiy.com/post/91403200
<br>Dmitry Baranovskiy 的博客中有篇文章,其中有五段小代码，用来测试是否理解 JavaScript 的核心，闭包和作用域。

```
if (!("a" in window)) {
    var a = 1;
}
alert (a);
```

```
var a = 1,
    b = function a (x) {
        x && a (--x);
    };
alert (a);
```

```
function a (x) {
    return x * 2;
}
var a;
alert (a);
```

```
function b (x, y, a) {
    arguments[2] = 10;
    alert (a);
}
b(1, 2, 3);
```

```
function a () {
    alert (this);
}
a.call (null);
```
