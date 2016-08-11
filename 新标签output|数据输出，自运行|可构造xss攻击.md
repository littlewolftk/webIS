------
* 特性：`<output> `标签定义不同类型的输出，比如脚本的输出。
* 格式：`<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0<br>
        <input type="range" id="a" value="50">100<br>
         +<input type="number" id="b" value="50"><br>
         =<output name="x" for="a b"></output><br>
       </form> `
* 属性方法：for 	element_id 	定义输出域相关的一个或多个元素。<br>
           form 	form_id 	定义输入字段所属的一个或多个表单。<br>
           name 	 name 	  定义对象的唯一名称。（表单提交时使用）
           
------
安全性：可以用来伪造隐藏XSS攻击，绕过过滤器和黑名单；<br>
        如利用poster、autofocus、onerror、formaction、oninput等属性，<br>
        输出脚本JS，实现XSS攻击或CSRF劫持。<br>
------
攻击典例：
        `<form oninput="javascript:0">0<br>
        <output name="x" for="a b" formatiion="javascript:alart(1)"></output><br>
       </form> `
