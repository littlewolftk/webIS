------
* 特性：embed可以用来插入各种多媒体，格式可以是 Midi、Wav、AIFF、AU、MP3等等，<br>
       Netscape及新版的IE 都支持。url为音频或视频文件及其路径，可以是相对路径或绝对路径。
* 属性方法：类似于` <audio> `和` <video>`<br>
      能够响应各属性事件
* 格式：`<embed src="your.mid">`

------
安全性：和`<audio>` 和 `<video>`相同<br>
        相对于之前的攻击方式大多都会被short和medisity(忘了怎么拼了）的规则限制住，无法生效；<br>
        但对于新标签的利用，可以根据浏览器的插件与兼容性上入手！<br>
        同时对于新标签的新增事件响应，也有许多反射型XSS的植入点，例如poster、autofocus、onerror、formaction、oninput等
        
-----
典例：
     `<video onerror="javascript:alert(1)" src="xxx"> `

