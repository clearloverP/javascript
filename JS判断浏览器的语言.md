## 兼容性写法
```
  // navigator.systemLanguage针对IE低版本(IE5+)
  let lang = (navigator.systemLanguage ? navigator.systemLanguage : navigator.language);    // 获取浏览器配置语言
  
  lang = lang.substr(0, 2);     // 获取lang字符串的前两位，区分是否是中文，
  
  if(lang == 'zh'){
      console.log('中文浏览器');
  }else{
      console.log('非中文浏览器');
  };
  
  // 如果需要精确知道其他语言
  let lang = (navigator.systemLanguage ? navigator.systemLanguage : navigator.language).toLowerCase();    // 获取浏览器配置语言
  // 然后判断即可
```

name | IE6\IE7\IE8 |  Firefox\Chrome\Safari | Opera 
-|-|-|-
navigator.language | undefined | zh-CN | zh-CN |
navigator.userLanguage | zh-cn | undefined | zh-cn |
navigator.browserLanguage | zh-cn | undefined | zh-cn |
navigator.systemLanguage | zh-cn | undefined | undefined |
