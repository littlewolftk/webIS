------
* 特性：storage本地存储，似乎有点想起cookie，的确用法也类似于cookie。但是storage较cookie有不少好处：<br>
      存储量大；在客户端完成，不会请求客户端；<br>
      storage分为sessionStorage和localStorage。<br>
      1.sessionStorage  临时存储，当页面关闭的时候，本地存储也就消失。并且sessionStorage的数据是不会共享的。<br>
       2.localStorage 永久删除，可以手动删除数据，数据是共享的。
* 格式：`<script type="text/javascript">`<br>
       `localStorage.lastname="Smith";document.write(localStorage.lastname);`<br>
      ` </script>`
* 属性与方法：storage下有以下api：<br>
      window.sessionStorage和window.localStorage有以下4个方法：<br>
      setItem(): 设置数据，key\value类型，类型都是字符串 可以用获取属性的形式操作<br>
      getItem(): 获取数据，通过key来获取到相应的value removeItem():<br>
      删除数据，通过key来删除相应的value<br>
      clear(): 删除全部存储的值。用法如下：<br>
     ` window.localStorage.getItem('name')`<br>
      存储事件：<br>
      当数据有修改或删除的情况下，就会触发storage事件。不过，在对数据进行改变的窗口对象上是不会触发的，也就是说有两个及两个以上的窗口，当有数据改变的时候，除了自己本窗口意外的其他窗口对象都会触发storage事件。<br>
      该事件的event对象下有以下属性：<br>
      Key : 修改或删除的key值，如果调用`clear()`,key为null<br>
      newValue : 新设置的值，如果调用`removeStorage()`,key为null<br>
      oldValue : 调用改变前的value值<br>
      storageArea : 当前的storage对象<br>
      url : 触发该脚本变化的文档的url
* 格式典例：
      `window.addEventListener('storage',function(ev){  //当前页面的事件不会触`<br>
        `console.log( ev.key );`<br>
        `console.log( ev.newValue );`<br>
       ` console.log( ev.oldValue );`<br>
        `console.log( ev.storageArea );`<br>
       ` console.log( ev.url );`<br>
      `},false);`<br>
      
------
安全性：Cookie未来的替代品。有存储量大、稳定、存取简便的优点，缺点是安全性，<br>
      虽然每个域都会有它独立的Storage,但是使用跨域的手段依然能够取到非本域的Storage数据
      
------
典例：
     
