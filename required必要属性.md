### required必要属性
功能：指定某输入是否必需 <br>
声明方式：空白，则表格就不能提交 <br>
  * <.input type="text" name="someInput" required>
  * <.input type="text" name="someInput" required="required">

----
#####注：
可以用 
	< input type="text" name="test" required oninvalid="setCustomValidity('请输入！');" oninput="setCustomValidity('');" />
来在input没有输入值时执行计算，从而获得XSS的能力。
