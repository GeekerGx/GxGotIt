# iframe 标签
## 其他
### 5像素问题
问题：  
div高度大于iframe高度5px左右。  
原因：  
使用了HTML5的头部，在使用如下两个头部声明时会使iframe不能填满div，从而产生5px的高度差。  

```html
<!DOCTYPE html>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```

方案：  
添加样式 `display:block`或`vertical-align:bottom`  
> `display:block`块级对象：前后换行，从新的一行开始往下走，不依赖于包裹他的对象。  
> `vertical-align:bottom`内联对象：不会前后换行，不会从新的一行开始，而是从包裹它的内容一直往后走。  
