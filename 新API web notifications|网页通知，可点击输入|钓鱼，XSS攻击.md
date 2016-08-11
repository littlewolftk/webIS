------
* 特性：HTML5中的桌面提醒（web notifications）能够让用户得到实时的消息提醒。<br>
      这一功能目前只有google chrome（21.0+）和Safari（6.0+）以及火狐的新版本部分实现了
* 属性方法：requestPermission()  用户请求获得消息提醒的权限<br>
      checkPermission()   用于获取请求权限的状态值，并返回这个值<br>
      createNotification()    以纯消息的方式创建提醒消息，它接受三个参数：iconURL, title, body<br>
      createHTMLNotification()    以HTML方式创建消息提醒，它接受一个参数，即HTML消息文档的URL<br>
      同时还可以相应全局事件<br>
      onshow：当消息框显示的时候触发该事件；<br>
　　  onclick： 当点击消息框的时候触发该事件；<br>
　　  onclose：当消息关闭的时候触发该事件；<br>
　　  onerror：当出现错误的时候触发该事件；
* 格式： 

     ` if(window.Notification && Notification.permission !== "denied") {`<br>
          `Notification.requestPermission(function(status) {    // 请求权限`<br>
             `if(status === 'granted') {`<br>
                `  // 弹出一个通知`<br>
                 ` var n = new Notification('Title', {`<br>
                   `   body : 'I am a Notification',`<br>
                    `  icon : '../xx.png'`<br>
               `   });`<br>
                ` // 两秒后关闭通知`<br>
             `    setTimeout(function() {`<br>
                   `  n.close();`<br>
             `    }, 2000);`<br>
           `  }`<br>
       `  });`
         
------
安全性：Web Notifications让我们在浏览器中能够接收推送的消息通知,
        但是它由于可以以HTML方式创建消息提醒，有可能会被攻击者利用来构造虚假信息，诱惑用户点击或者输入个人信息，实现钓鱼。
        同时也可以在已有的消息提示框嵌攻击JS，通过事件触发JS，实现XSS攻击
------
典例:
     
        
