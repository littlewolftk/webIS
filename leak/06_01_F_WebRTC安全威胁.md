##特性：HTML5全面支持

WebRTC（Real-Time Communications (RTC))是基于HTML5的标准，各大主流浏览器均对WebRTC提供了支持。自2011年开源以来得到广泛的应用。

----
##环境：各主流浏览器均涉及

在HTML5新标准下，虽然各浏览器对WebRTC的实现略有不同，但是提供的WebRTC接口基本统一,只要能够支持Javascript的浏览器都能达到实时通讯的能力。

----
##漏洞能力：

在WebRTC接口统一的同时，也意味着NAT穿透等的实现变得方便。如果能够得到执行Javascript的机会，就能够发起针对浏览器所在内网的攻击。

----
##例子：
####下面是几个潜在的威胁和demo：
	针对内网进行扫描：	http://blog.skylined.nl/LocalNetworkScanner/
	识别使用VPN的用户所在的真正IP地址：	https://ipleak.net/
	打开摄像头麦克风等设备进行录制：	http://www.oschina.net/question/156697_172887
----
##防御：

目前没有比较好的防御方案。
####方案一：关闭Javascript。
评价：方便快捷，固然提高了浏览安全性，但是很大程度上影响了用户的浏览体验，因噎废食。
####方案二：使用插件屏蔽WebRTC。
评价：编写插件需要一定功夫，而且WebRTC作为HTML5的新特性被加入到标准中去自然有其存在的需求，这样屏蔽之实际上是阉割了H5的功能，安全与功效之间需要找寻一个新的平衡点。
