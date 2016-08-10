-----

* 浏览器支持：Firefox 4.0以上，Opera 10.5以上，Chrome 10.0以上，Safari 4.0.4以上
* 特性：form新特性
* 环境：需要用户点击提交。
* 漏洞类型：XSS

-----

举例：
------

`<form id="test"></form><button form="test" formaction="javascript:alert(1)">X</button>`


防御：
----

不要让用户提交包含 "form" 和 "formaction"属性的标签.避免在form中出现id属性及提交按钮.


