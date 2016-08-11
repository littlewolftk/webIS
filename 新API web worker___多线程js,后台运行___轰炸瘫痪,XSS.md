------
* 特性：Web Workers 是 HTML5 提供的一个javascript多线程解决方案，我们可以将一些大计算量的代码交由web Worker运行而不冻结用户界面。<br>
       Web Worker的基本原理就是在当前javascript的主线程中，使用Worker类加载一个javascript文件来开辟一个新的线程，起到互不阻塞执行的效果.
* 属性方法：提供主线程和新线程之间数据交换的接口：postMessage，onmessage。
* 格式：`var worker =new Worker("worker.js"); `//创建一个Worker对象并向它传递将在新线程中执行的脚本的URL<br>
       `worker.postMessage("hello world");`     //向worker发送数据<br>
       `worker.onmessage =function(evt){ `    //接收worker传过来的数据函数<br>
      ` console.log(evt.data); `             //输出worker发送来的数据<br>
      }
      同时WORKER还能做AJAX和JONP的事情，只是用时略长
      
-----
安全性：由于worker独立运行，额外线程，利用WebWorker大规模执行多线程攻击，例如DDos攻击、发送垃圾邮件或者进行网络嗅探。<br>
        WebWorker无法访问DOM，只能通过postMessageAPI和主线程通信。postMessage在HTML5中被引入，用来解决跨域或者跨线程数据交互的问题。但是如果messaging可以接收任何来源的信息，此页面有可能会被攻击；<br>
        另外postMessage不通过服务器，如果不经过验证和过滤，可能成为XSS注入点。

-----
典例：
