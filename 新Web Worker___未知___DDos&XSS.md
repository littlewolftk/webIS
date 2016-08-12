
WebWorker介绍
------
 由于JavaScript是单线程执行的，在执行过程中浏览器不能执行其它JavaScript脚本，UI渲染线程也会被挂起，<br>
 从而导致浏览器进入僵死状态。使用WebWorker可以将计算过程放入一个新线程里去执行将避免这种情况的出现。<br>
 这样我们可以同时执行多个JS任务而不会阻塞浏览器，非常适合异步交互和大规模计算，这在以前是很难做到的。<br>

攻击
------
* DDos攻击、发送垃圾邮件.
  *用户一旦访问恶意页面或者网站时，页面的恶意代码就能把用户的浏览器当作肉鸡，<br>
  利用WebWorker大规模执行多线程攻击，例如DDos攻击、发送垃圾邮件或者进行网络嗅探。
* XSS攻击
  * WebWorker无法访问DOM，只能通过postMessageAPI和主线程通信。
  * postMessage在HTML5中被引入，用来解决跨域或者跨线程数据交互的问题。但是如果messaging可以接收任何来源的信息，此页面有可能会被攻击；
  * postMessage不通过服务器，如果不经过验证和过滤，可能成为XSS注入点。
  
###举例
如下代码没有对输入数据进行验证和清洗，攻击者完全可以构造恶意的data来注入页面DOM，构造XSS攻击，形如“><script></script>”等等。

`worker.addEventListener(‘message’,function(e) {   ` <br>
 `  document.getElementById(‘result’).innerHTML = e.data;`    <br>
`}, false); ` <br>

防御
------
* 对于用户来说，不要访问不安全的站点。
* 使用postMessage时需要验证来源可信
* 不要使用innerHTML，现代浏览器提供了textContent属性，可以帮助对HTML标签进行过滤，或者你可以自行编写过滤的逻辑和函数。
