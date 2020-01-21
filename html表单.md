表单标签
1、<form></form>标签：所有的表单标签都要放在form标签内部,每一个form标签代表
                                          一个表单，一个页面中表单不止一个。
                               属性：①name 表单名称（命名
                                               <form name=" "></form>
                                          ②method 提交方式（指定get或者post的提交方式 
                                               <form method="post"></form>
                                          ③action 提交地址（指定数a据提交到哪个地址处理
                                               <form action="index.php"></form>
                                          ④target 打开方式（指定窗口打开方式，一般是_blank
                                               <form target="_blank"></form>
                                          ⑤enctype 编码方式（一般不设置
2、input标签：<input type="表单类型" />（自闭合标签）
                   type属性值：①text 单行文本框
                                                 text的属性值：i:value(文本框的默认显示文字)
                                                                           <input type="text" value="内容" />
                                                                        ii:size(文本框长度)
                                                                       iii:maxlength(文本最长限度)(CTF有修改
                                                                                                                        长度的题目)
                                         ②password 密码文本框
                                         ③radio 单选框
                                                       <input type="radio" name="组名" vlaue="取值" />
                                                       一组只能选其中一项，所以要确定好组名,否则能多选
            check表示默认选项 <input type="radio" name="组名" value="取值" check />
                                         ④checkbox 多选框：和单选框结构一样
                                         ⑤button或submit或reset 按钮
                                          (点击弹窗)<input type="button" value="按钮上的文字" />
                    (提交数据给服务器)<input type="submit" value="按钮上的文字" />
                    (清除用户输入的数据)<input type="reset" value="按钮上的文字" />
                                         ⑥file 文件上传
                                                                 <input type="file" />
3、textarea标签
                           输入多行文本框只能用textarea不能用input
                           <textarea row="行数" cols="列数" value=" ">默认内容</textarea>
4、select标签和option标签之下拉列表(点击下展)
                          <select>
                                  <option>选项内容</option>                          
                                  <option>选项内容<option>
                           </select>
      <select multiple>更改为多选
      <select size="显示几个列表项">
      <option selected>初始默认选中
      <option value="选项值">

