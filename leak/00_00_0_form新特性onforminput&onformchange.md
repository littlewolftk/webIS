-----

* 浏览器支持：Opera 10.5、Opera 12.0
* 特性：form新特性
* 环境：用户输入。
* 漏洞类型：XSS

-----

举例：
------

`<form id=test onforminput=alert(1)><input></form><button form=test onformchange=alert(2)>X</button>`


防御：
----

不要让用户提交包含 "onformchange" 和 "onforminput"属性的标签.避免在form中出现id属性及提交按钮.


