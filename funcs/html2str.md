# html符号转化成字符串
## 说明：在有些需要显示的地方进行转化，不然这些符号会被解析，从而无法在页面上显示。比如: ``` <tT ```,显示的时候不进行转化,则页面上无法正常显示。

## 案例：
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
<div>
    <tT
</div>
</body>
</html>
```
### 开发者工具效果,如下图所示:


## 解决方案，定义简单函数如下：
```
function html2str(str) {
	return str.replace(/[<>&"]/g, function(c) {
		return {'<':'&lt', '>':'&gt', '&':'&amp;', '"':'&quot;'}[c];
	});
}
```

## 最终代码如下：
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="jquery-1.11.3.min.js"></script>
</head>
<body>
<div id="admin">

</div>
<script>
function html2str(str) {
    return str.replace(/[<>&"]/g, function(c) {
	return {'<':'&lt', '>':'&gt', '&':'&amp;', '"':'&quot;'}[c];
    });
}
$("#admin").html(html2str("<tT"));
</script>
</body>
</html>
```

### 最终效果如下：

