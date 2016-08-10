-----

* 浏览器支持：Opera 10.5以上、Chrome 10.0以上、Firefox 4.0以上、Safari 4.0.4以上、IE10.0以上
* 特性：form新特性
* 环境：用户输入。
* 漏洞类型：XSS

-----

举例：
------

```

<form><button formaction="javascript:alert(1)">X</button>

```


防御：
----

不要让用户提交包含 "form"和"formaction"的属性，或者转换其为伪属性。

