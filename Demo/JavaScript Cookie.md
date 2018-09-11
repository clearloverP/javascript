## 什么是 Cookie
 ```Cookie``` 是一些数据, 存储于你电脑上的文本文件中。
 当 web 服务器向浏览器发送 web 页面时，在连接关闭后，服务端不会记录用户的信息。
 Cookie 的作用就是用于解决 "如何记录客户端的用户信息":
 当用户访问 web 页面时，他的名字可以记录在 ```cookie ```中。
 在用户下一次访问该页面时，可以在``` cookie ```中读取用户访问记录。
Cookie 以名/值对形式存储，如: ```username=John Doe```

## 使用 JavaScript 创建Cookie
JavaScript 可以使用 document.cookie 属性来创建 、读取、及删除 cookie。
JavaScript 中，创建 cookie 如下所示：
```document.cookie="username=John Doe";```
您还可以为 cookie 添加一个过期时间（以 UTC 或 GMT 时间）。默认情况下，cookie 在浏览器关闭时删除：
```document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT";```
您可以使用 path 参数告诉浏览器 cookie 的路径。默认情况下，cookie 属于当前页面。
```document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT; path=/";```

## 使用 JavaScript 读取 Cookie
在 JavaScript 中, 可以使用以下代码来读取 cookie：
```var x = document.cookie;```

## 使用 JavaScript 修改 Cookie
在 JavaScript 中，修改 cookie 类似于创建 cookie，如下所示： 旧的 cookie 将被覆盖。
```document.cookie="username=John Smith; expires=Thu, 18 Dec 2013 12:00:00 GMT; path=/";```

## 使用 JavaScript 删除 Cookie
删除 cookie 非常简单。您只需要设置 expires 参数为以前的时间即可，如下所示，设置为 Thu, 01 Jan 1970 00:00:00 GMT: 注意，当您删除时不必指定 cookie 的值。
```document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT";```
