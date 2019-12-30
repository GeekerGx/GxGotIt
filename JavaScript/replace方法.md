# replace()方法

## 语法

> `string.replace(subString|RegExp,string|funcion)`  
主要用法是：第一个参数为正则，第二个参数为需要替换的值。

## replace(string,string)

```js
"this is that issue".replace('is','Is');
// "thIs name is {name}"
```

只把第一个is字符串替换成Is。  
因为这边没用到正则的全局匹配，所以默认只替换第一个。  
> 关键字使用

```js
"this is that issue".replace('is','$&');
"this is that issue".replace('is','$`');
"this is that issue".replace('is',"$'");
```

|字符|替换文本|
|-|-|
|$1、$2、...、$99|与 regexp 中的第 1 到第 99 个子表达式相匹配的文本。|
|$&|与 regexp 相匹配的子串。|
|$`|位于匹配子串左侧的文本。此处为反引号|
|$'|位于匹配子串右侧的文本。此处为单引号|

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
