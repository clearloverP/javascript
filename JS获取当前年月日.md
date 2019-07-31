## 1、获取当前月份
```
function handleMonth() {
  let nowMonth = new Date().getMonth() + 1;    // 月份从0开始，所以需要加1
  
  if (nowMonth.toString().length == 1 ) {
    nowMonth = '0' + nowMonth;
  }
  
  return nowMonth;
}

// 调用
handleMonth();        // "08"
```

## 2、获取当前年份 
```
  function getYear() {
    return new Date().getFullYear();
  }
  
  getYear();     // 2019
```

## 3、获取当前年月
```
  // 参数separator: 表示年份和月份之间的分隔符，String类型，默认为"-"
  function getYearMonth(separator='-') {
    let date = new Date();
    let y = date.getFullYear();
    let m = date.getMonth() + 1;
    
    if (m.toString().length == 1) {
      m = '0' + m;                    // 小于10的月份前面补0
    }
    
    if (separator.length == 0) {
       separator = '-';               // 分隔符为''的，用"-"替换
    }
    
    return y + separator + m;
  }
  getYearMonth();
```

```
  // 补0函数
  function addZero(num) {
    if (num.toString().length == 1) {
      num = '0' + num;
    }
    
    return num;
  }
  
  addZero(2);     // 2
```

## 4、获取当前年月日
```
  // separator为间隔符，String类型，默认为'-'
  function getYMD(separator='-') {
    let date = new Date();
    let y = date.getFullYear();
    let m = date.getMonth() + 1;
    let d = date.getDate();
    
    if (separator.length == 0) {
      separator = '-';
    }
    
    m = addZero(m);
    d = addZero(d);
    
    return y + separator + m + separator + d;
  }
  
  getYMD();           // 2019-07-31
  
  // 或者可以用如下方式：
  let a = new Date().toLocaleDateString();      // 2019-07-31
  a = a.replace(/\//g, '-');
  console.log(a);
```

## 5、获取当前时间戳（精确到毫秒）
```
// 方法一：
var timestamp = (new Date()).valueOf();

// 方法二：
var timestamp = new Date().getTime();
```

## 6、将时间戳转换成日期格式
```
// 方法一：
function getLocalTime(nS) {     
    return new Date(parseInt(nS) * 1000).toLocaleString().substr(0,17)
}

console.log(getLocalTime(new Date().getTime() / 1000));       // 2019/7/31 下午3:25:14

// 方法二：
function getLocalTime(nS) {     
    return new Date(parseInt(nS) * 1000).toLocaleString().replace(/年|月/g, "-").replace(/日/g, " ");      
} 

console.log(getLocalTime(new Date().getTime() / 1000));       // 2019/7/31 下午3:25:14
```









