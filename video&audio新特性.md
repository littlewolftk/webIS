视频: `<video>`
------
* 标签属性：autoplay, contros, height, loop, preload, src, width
* 方式：使用 DOM 进行控制
* 格式：ogg(ogv), mp4

举例：<br>
<.video controls preload>. 
<.source src="cohagenPhoneCall.ogv" type="video/ogg; codecs='vorbis, theora'" /> <br>
<.source src="cohagenPhoneCall.mp4" type="video/mp4; 'codecs='avc1.42E01E, mp4a.40.2'" /> <br>
<.p>. Your browser is old. <.a href="cohagenPhoneCall.mp4">.Download this video instead.</.a>. </.p> <br>
</.video> <br>


音频:`<audio>`
------
* 标签属性：autoplay, contros, preload,src
* 格式：ogg(oga), mp3, wav, AAC

举例： <br>
<.audio autoplay="autoplay" controls="controls"><br>
     <.source src="file.ogg" /><br>
     <.source src="file.mp3" /><br>
     <.a href="file.mp3">.Download this file.</.a><br> 
</.audio>

------
不同浏览器支持方式不同

