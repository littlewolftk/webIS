------
* 特性：`<audio>` 标签用于定义声音，比如音乐或其他音频流。<br>
    对比H4代码：`HTML5:<audio src="someaudio.wav">您的浏览器不支持 audio 标签。</audio>`<br>
                 `HTML4:<object type="application/ogg" data="someaudio.wav"><param name="src" value="someaudio.wav"></object>`<br>
    对于兼容此代码的浏览器，播放时不再需要插件的存在，Internet Explorer 9+, Firefox, Opera, Chrome 以及 Safari 支持` <audio>`<br> 标签
* 属性与方法： 新属性    属性值<br>
    autoplay 	autoplay 	如果出现该属性，则音频在就绪后马上播放。<br>
    controls 	controls 	如果出现该属性，则向用户显示控件，比如播放按钮。<br>
    loop 	     loop 	  如果出现该属性，则每当音频结束时重新开始播放。<br>
    muted 	   muted 	  规定视频输出应该被静音。<br>
    preload 	preload   如果出现该属性，则音频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。<br>
    src 	      url 	  要播放的音频的 URL。<br>
    同时许多事件能够响应<br>
    abort 	当音频/视频的加载已放弃时<br>
    canplay 	当浏览器可以播放音频/视频时<br>
    canplaythrough 	当浏览器可在不因缓冲而停顿的情况下进行播放时<br>
    durationchange 	当音频/视频的时长已更改时<br>
    emptied 	当目前的播放列表为空时<br>
    ended 	当目前的播放列表已结束时<br>
    error 	当在音频/视频加载期间发生错误时<br>
    loadeddata 	当浏览器已加载音频/视频的当前帧时<br>
    loadedmetadata 	当浏览器已加载音频/视频的元数据时<br>
    loadstart 	当浏览器开始查找音频/视频时<br>
    pause 	当音频/视频已暂停时<br>
    play 	当音频/视频已开始或不再暂停时<br>
    playing 	当音频/视频在已因缓冲而暂停或停止后已就绪时<br>
    progress 	当浏览器正在下载音频/视频时<br>
    ratechange 	当音频/视频的播放速度已更改时<br>
    seeked 	当用户已移动/跳跃到音频/视频中的新位置时<br>
    seeking 	当用户开始移动/跳跃到音频/视频中的新位置时<br>
    stalled 	当浏览器尝试获取媒体数据，但数据不可用时<br>
    suspend 	当浏览器刻意不获取媒体数据时<br>
    timeupdate 	当目前的播放位置已更改时<br>
    volumechange 	当音量已更改时<br>
    waiting 	当视频由于需要缓冲下一帧而停止
    
------
安全性：对于这个新出来的声效标签，安全漏洞和之前h4的img和object类似，都是可以外部获取url内嵌攻击代码；<br>
        不过对于之前的攻击方式大多都会被short和medisity(忘了怎么拼了）的规则限制住，无法生效；<br>
        但对于新标签的利用，可以根据浏览器的插件与兼容性上入手！<br>
        同时对于新标签的新增事件响应，也有许多反射型XSS的植入点。

------        
典例： 
     `<video><source onerror="javascript:alert(1)“>  `
