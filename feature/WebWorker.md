***

- 特性：WebWorker
- 介绍：利用WebWorker可将计算过程放入一个新线程去执行，使JS可以多线程执行。
- 原理：当在 HTML 页面中执行脚本时，页面的状态是不可响应的，直到脚本已完成。<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;web worker 是运行在后台的 JavaScript，独立于其他脚本，不会影响页面的性能。您可以继续做任何愿意做的事情：点击、选取内容等等，而此时 web worker 在后台运行。
- 攻击：
	- Botnet - 包括DDos、发送垃圾邮件等
	- postMessage带来的问题 - WebWorker利用PostMessage与主线程通信。但messaging一接收任何来源的信息、二部通过服务器，极易成为XSS注入点。
- 漏洞类型：DDos、XSS
- 预防：
	- 对于用户不要访问不安全站点
	- 使用postMessage时需要验证来源可信；另外不要使用innerHTML，现代浏览器提供了textContent属性，可以帮助对HTML标签进行过滤，或者你可以自行编写过滤的逻辑和函数。

## 举例

<pre>
worker.addEventListener(‘message’,function(e) {    
   document.getElementById(‘result’).innerHTML = e.data;    
}, false);  
</pre>