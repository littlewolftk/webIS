-----

* 特性：input新特性
* 环境：不需要用户交互。
* 漏洞类型：XSS

-----

举例：
------

`<input onfocus=write(1) autofocus>`


防御：
----

检测用户提交的内容中是否含有"autofocus"属性。


