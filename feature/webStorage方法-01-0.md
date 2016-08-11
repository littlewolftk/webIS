***

- 特性：webStorage 方法
- 介绍：为解决Cookie存储数据容量小、存取不便、易被清除的问题，H5提供WebStorage。
	- localStorage - 没有时间限制的数据存储
	- sessionStorage - 针对一个session的数据存储。
- 原理：之前数据存储均由Cookie完成，但Cookie不适合大量数据的存储，因为它们由每个对服务器的请求来传递，这使得Cookie速度很慢而且效率也不高。<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;在HTML5中，数据不是由每个服务器请求传递的，而是只有在请求时使用数据。它使在不影响网站性能的情况下存储大量数据成为可能。
- 攻击：利用javascript进行XSS攻击窃取信息，例如用户token或者资料。
- 漏洞类型：XSS
- 防御：
	- 数据放在合适的作用域里
	- 不要储存敏感信息

## 举例

<pre>
if(localStorage.length){    
         for(I in localStorage) {    
                   console.log(i);    
                   console.log(localStorage.getItem(i));    
         }    
}
</pre>

***

**注意：**

部分编程者为了方便会把很多关键信息放在全局变量里，例如用户名、密码、邮箱等等。数据放在不合适的作用域里会带来严重的安全问题。

## 举例

下面的脚本可遍历全局变量来获取信息

<pre>
for(iin window) {    
         obj=window[i];    
         if(obj!=null||obj!=undefined)    
             var type =typeof(obj);    
         if(type=="object"||type=="string") {    
             console.log(“Name:”+i);    
             try {    
                 my = JSON.stringify(obj);    
                 console.log(my);    
             } catch(ex) {}    
         }    
} 
</pre>
