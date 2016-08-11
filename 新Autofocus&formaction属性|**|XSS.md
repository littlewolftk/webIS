### `Autofocus & formaction`属性：
功能：特定的输入是“选择”或聚焦，默认情况下，实现自动聚焦。，而formaction属性能覆盖 form 元素的action 属性。

攻击： XSS攻击
举例：<br>
`<inputautofocus onfocus=“alert(1)”> `    <br>
`<form><buttonformactionbuttonformactionbuttonformactionbuttonformaction="javascript:alert(1)">  ` <br>
例如攻击者输入`http://www.yujie.com/1.php?text=<videoposter=”javascript:alert(1)”>`时就能立即运行攻击脚本。

### 防御：
对前端或者后端的过滤器进行优化，添加过滤规则或者黑名单。
