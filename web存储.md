 客户端存储数据：
 ------
 数据不是由每个服务器请求传递的，而是只有在请求时使用数据。HTML5 使用 JavaScript 来存储和访问数据。
 
### `localStorage` - 没有时间限制的数据存储
* 创建访问 localStorage
  * 实例: <br />
 `<script type="text/javascript">localStorage.lastname="Smith";document.write(localStorage.lastname);</script>`

### `sessionStorage` - 针对一个 session 的数据存储
* 创建访问sessionStorage
  * 实例: <br />
  `<script type="text/javascript">sessionStorage.lastname="Smith";document.write(sessionStorage.lastname);</script>`
