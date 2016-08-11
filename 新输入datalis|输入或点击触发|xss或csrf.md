------

* 特性：自定义选项列表，需与 input 元素配合使用，通过input 元素的 list 属性来绑定，用来定义 input 可能的值。
       datalist 及其选项不会被显示出来，它仅仅是合法的输入值列表。
       性质略同H4的复选框。
* 格式：<input id=”fruits” list=”fruits” />
       <datalist id=”fruits”>
       <option value=”Apple”>
       <option value=”Banana”>
       </datalist>
* 属性方法：支持HTML5的全局属性和事件属性。

------

安全性：代替H4的复选框，由于新属性poster、autofocus、onerror、formaction、oninput等的出现
        或可将JS攻击直接引入其中，不再依赖于input的输入框，而老版本的过滤器主要针对提交选框，
        所以导致XSS和CSRF跨域请求伪造。
        
------

攻击猜测：
        <form>
        <input>
        <datalist formaction="javascript:alert(1)" id="fruits”>
        <option value=”Apple”>
        <option value=”Banana”>
        </datalist>
        当输入提交及运行攻击代码
