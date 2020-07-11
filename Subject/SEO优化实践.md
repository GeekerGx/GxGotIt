# SEO优化实践
## 百度-搜索资源平台
### 用户中心-站点管理-添加网站
#### 输入网站
#### 站点属性
#### 验证网站
##### 文件验证
下载提示的验证文件并将其放在站点根目录下。
##### HTML标签验证
在网站首页的head中添加对应的meta标签。
##### CNAME验证
子域名通过CNAME解析到ziyuan.baidu.com。
### 资源提交-普通收录-手动提交
直接填写站点页面地址进行提交。
### 自动推送工具（自动推送代码）
> 文档说明  
> https://ziyuan.baidu.com/college/courseinfo?id=267&page=2#h2_article_title18  

```js
(function () {
    var bp = document.createElement('script');
    var curProtocol = window.location.protocol.split(':')[0];
    if (curProtocol === 'https') {
        bp.src = 'https://zz.bdstatic.com/linksubmit/push.js';
    } else {
        bp.src = 'http://push.zhanzhang.baidu.com/push.js';
    }
    var s = document.getElementsByTagName("script")[0];
    s.parentNode.insertBefore(bp, s);
})();
```

## 360-360站长平台
### 我的站点-站点管理-添加网站
#### 输入网站
#### 验证
##### 代码验证
在网站首页的head中添加对应的meta标签。
##### 文件验证
下载提示的验证文件并将其放在站点根目录下。
##### CNAME验证
子域名通过CNAME解析到ziyuan.baidu.com。
### 数据提交-自动收录

```js
(function () {
    var src = "https://jspassport.ssl.qhimg.com/11.0.1.js?d182b3f28525f2db83acfaaf6e696dba";
    document.write('<script src="' + src + '" id="sozz"><\/script>');
})();
```
