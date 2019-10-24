# replace()方法
## 语法
> `string.replace(string|RegExp,string|funcion)`
## replace(string,string)
```js
"this is that issue".replace('is','Is');
// "thIs name is {name}"
```
只把第一个is字符串替换成Is。  

```js
"this is that issue".replace('is','$&');
"this is that issue".replace('is','$`');
"this is that issue".replace('is',"$'");
```

## replace(RegExp,string)
```js
"this is that issue".replace(/i\w*s/g,'Is');
// "thIs Is that Isue"
```
直接把所有符合正则的字符串替换成Is。
其中包括this中的is、is、issue中的iss。

```js
"this is that issue".replace(/i(\w*)s/g,'$1');
"this is that issue".replace(/(i)(\w*)s/g,'$2');
"this is that issue".replace(/(i)(\w*)(s)/g,'$3');
```

## replace(string,funcion)
```js
"this is that issue".replace('is',function(){
    console.log(arguments);
});
//  ["is", 2, "this is that issue"]
```
第一个参数为匹配到的字符串  
第二个参数为匹配到的索引  
第三个参数为替换前的字符串  
## replace(RegExp,funcion)
```js
"this is that issue".replace(/i\w*s/g,function(){
    console.log(arguments);
});
//  ["is", 2, "this is that issue"]
//  ["is", 5, "this is that issue"]
//  ["iss", 13, "this is that issue"]
```
第一个参数为匹配到的字符串  
第二个参数为匹配到的索引  
第三个参数为替换前的字符串  
```js
//正则中包含一个括号
"this is that issue".replace(/i(\w*)s/g,function(){
    console.log(arguments);
});
//  ["is", "", 2, "this is that issue"]
//  ["is", "", 5, "this is that issue"]
//  ["iss", "s", 13, "this is that issue"]

//正则中包含多个括号
"this is that issue".replace(/(i)(\w*)(s)/g,function(){
    console.log(arguments);
});
//  ["is", "i", "", "s", 2, "this is that issue"]
//  ["is", "i", "", "s", 5, "this is that issue"]
//  ["iss", "i", "s", "s", 13, "this is that issue"]
```
从中可以看出：
第一个参数为匹配到的字符串  
中间部分即为各个括号匹配到的子字符串  
倒数第二个参数为匹配到的索引  
倒数第一个参数为替换前的字符串  
即形式为：`[正则匹配结果,...[分组匹配结果],索引,原字符串]`