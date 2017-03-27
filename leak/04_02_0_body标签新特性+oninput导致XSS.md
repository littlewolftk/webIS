-----

* 浏览器支持：Firefox 3.6以上、Opera 9.0以上、Safari 4.0以上、Chrome 4.0以上、IE10.0以上
* 特性：body标签新特性，通过用户在输入框中输入触发<Body>的oninput执行Javascript.
* 环境：需要用户在输入框中输入触发事件。
* 漏洞类型：XSS

-----


举例：
------

`<body oninput=alert(1)><input autofocus>`


防御：
----

白名单过滤oninput防止出现xss。


