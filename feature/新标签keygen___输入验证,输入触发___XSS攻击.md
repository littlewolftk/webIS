------
* 特性：
    <keygen> 标签规定用于表单的密钥对生成器字段。<br>
    当提交表单时，私钥存储在本地，公钥发送到服务器。<br>
    <keygen>标签所期望的是在收到SPKAC(SignedPublicKeyAndChallenge)排列后，服务器会生成一个客户端证书(Client Certificate)，然后返回到浏览器让用户去下载保存到本地。<br>
    之后，用户在需要验证的时候，使用本地存储的私钥和证书后通过TLS/SSL安全传输协议到服务端做验证。
* 格式：
    `<form action="demo_keygen.asp" method="get">`<br>
    `  Username: <input type="text" name="usr_name" />`<br>
    `   Encryption: <keygen name="security" />`<br>
    `  <input type="submit" />`<br>
    </form>
* 属性：
    autofocus 	disabled 	使 keygen 字段在页面加载时获得焦点。<br>
    challenge 	challenge 	如果使用，则将 keygen 的值设置为在提交时询问。<br>
    disabled 	disabled 	  禁用 keytag 字段。<br>
      form 	  formname   	定义该 keygen 字段所属的一个或多个表单。<br>
      keytype   	rsa     定义 keytype。rsa 生成 RSA 密钥。<br>
      name   	fieldname   定义 keygen 元素的唯一名称。name 属性用于在提交表单时搜集字段的值。<br>
      
------
安全性：
    1.验证保密性不强。没有在一个标准的位置存储私钥；没有标准的key长度或者hash来实现浏览器无关性；<br>
      &nbsp;浏览器依赖过于严重；签名只能基于MD5，而不能使用其他的加密算法；<br>
      &nbsp;可以修改<keygen>标签生成的本地的表单内容，从而直接降低了key的安全成。<br>
    2.工作效率鸡肋，本地存储私钥，并且加密形式受浏览器影响，用户在使用过程中的任何变动都会使验证过程受影响；<br>
    3.新标签响应autofocus和challenge属性，可嵌入xss代码外部劫持，由于标签的少见性，可绕过浏览器的规则和黑名单；
    
------
典例：
    <form action="xxx" method="get">`<br>
    `  Username: <input type="text" name="usr_name" formaction="javascript:alert(1)"/>`<br>
    `   Encryption: <keygen name="security" onfocus="alert(1)"/>`<br>
    `  <input type="submit" />`<br>
    </form>
