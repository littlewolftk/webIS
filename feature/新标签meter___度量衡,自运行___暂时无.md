------
* 特性：定义度量衡。仅用于已知最大和最小值的度量。
* 属性方法：form 	form_id 	规定 <meter> 元素所属的一个或多个表单。<br>
          high 	number 	规定被视作高的值的范围。<br>
          low 	number 	规定被视作低的值的范围。<br>
          max 	number 	规定范围的最大值。<br>
          min 	number 	规定范围的最小值。<br>
          optimum 	number 	规定度量的优化值。<br>
          value 	number 	必需。规定度量的当前值。
* 格式：`<meter value="3" min="0" max="10">十分之三</meter><br>
       <meter value="0.6">60%</meter>`
       
------
安全性：基本无属性方法安全漏洞，
        类似进度条progress。
