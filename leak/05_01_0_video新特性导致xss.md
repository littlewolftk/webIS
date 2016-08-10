-----

* 浏览器支持：Firefox 3.5以上、IE9.0以上
* 特性：video新特性，onerror可以引入事件处理JS
* 环境：不需要用户交互。
* 漏洞类型：XSS

-----

举例：
------

```
<video onerror="alert(1)"><source></source></video>
```


防御：
----

确认用户提交的<source>标签中不存在事件处理的JS，或者为事件处理函数添加一个白名单过滤。


