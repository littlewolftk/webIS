-----

* 浏览器支持：Opera 10.5以上，Chrome 4.0以上，Firefox 4.0以上
* 特性：video新特性，source标签onerror可以引入JS
* 环境：不需要用户交互。
* 漏洞类型：XSS

-----

举例：
------

```
<video><source onerror="alert(1)">
```


防御：
----

确认用户提交的<source>标签中不存在事件处理的JS，或者为事件处理函数添加一个白名单过滤。


