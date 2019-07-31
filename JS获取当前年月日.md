一下调用时默认时间设置为：2019-08-01 08：08：21

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

## 4、获取当前月日
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
```












