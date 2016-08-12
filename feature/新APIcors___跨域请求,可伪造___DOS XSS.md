------
* 特性：CORS通过服务器增加一个特殊的Header[Access-Control-Allow-Origin]来告知客户端跨域的限制，如果浏览器支持CORS的话，如果判断Origin通过的话，就会允许XHR进行请求，而不需要再使用jsonP或者代理文件。<br>
      如果浏览器检测到相应的设置，就可以允许Ajax进行跨域的访问。<br>
      浏览器支持：<br>
      Feature    	Chrome 	Firefox (Gecko) 	Internet Explorer    	Opera 	Safari<br>
      Basic support 	4 	    3.5         8 (via XDomainRequest)10 	  12    	4<br>
* 属性方法：<br>
      `Access-Control-Allow-Origin: http://foo.example`<br>
      `Access-Control-Allow-Methods: POST, GET, OPTIONS`<br>
     ` Access-Control-Allow-Headers: X-PINGOTHER`<br>
     ` Access-Control-Max-Age: 1728000`<br>

------
安全性：HTTP头只能说明请求来自一个特定的域，但是并不能保证这个事实。因为HTTP头可以被伪造。<br>
      即便页面只允许来自某个信任网站的请求，但是它也会收到大量来自其他域的跨域请求。.这些请求有时可能会被用于执行应用层面的DDOS攻击，并不应该被应用来处理。<br>
      要击垮这个网站，攻击者可以利用XSS漏洞将Javascript脚本注入某个公共论坛中，当用户访问这个论坛时，使用它的浏览器重复执行这个到服务器的搜索请求。或者即使不采用跨域请求，使用一个目标地址包含请求参数的图像元素也可以达到同样的目的。<br>
      如果可能的话，攻击者甚至可以创建一个WebWorker执行这种攻击。这会消耗服务器大量的资源。<br>
      攻击者已经确定了你可以全域访问的productsearch.php页面上存在SQL注入漏洞。<br> 攻击者并不是直接从它们的系统数据库中获取数据，他们可能会编写一个JavaScript数据采集脚本，并在自己的网站或者存在XSS问题的网站上插入这段脚本。当受害者访问含有这种恶意JavaScript脚本的网站时，它的浏览器将执行针对“productsearch.php”的SQL注入攻击，采集所有的数据并发送给攻击者。<br>

------
典例：
