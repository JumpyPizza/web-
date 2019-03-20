在css中，选择图片作为背景：background:url() no-repeat; 不进行平铺；repeat-y 进行垂直平铺。可以设置width 和 height。在no-repeat后面可以设置定位  
css中定义的类中有标签，如a标签，可以通过.class a选中，可以设置.class a:hover{color:blue; text-decoration:underline;}设置鼠标悬停在上面时有颜色，并且出现下划线
对一个\<li>标签采用float:left，它就会向左浮动，从左到右排列。定位：position:absolute;绝对定位，后面输入位置，比如left:30px;top:20px;  
父标签的位置设为relative后，底下的子标签的位置absolute就是相对于父标签的。  

想在标题的地方加图片，可以为标题\<h>设置一个背景图片，然后为\<h>加上\<font>，然后在样式中font{dispaly:none}   
text-indent:2em; 缩进两字符

现代的辅助技术能够识别并朗读由 CSS 生成的内容和特定的 Unicode 字符。为了避免 屏幕识读设备抓取非故意的和可能产生混淆的输出内容（尤其是当图标纯粹作为装饰用途时），我们为这些图标设置了 aria-hidden="true" 属性。

如果你使用图标是为了表达某些含义（不仅仅是为了装饰用），请确保你所要表达的意思能够通过被辅助设备识别，例如，包含额外的内容并通过 .sr-only 类让其在视觉上表现出隐藏的效果。

如果你所创建的组件不包含任何文本内容（例如， <button> 内只包含了一个图标），你应当提供其他的内容来表示这个控件的意图，这样就能让使用辅助设备的用户知道其作用了。这种情况下，你可以为控件添加 aria-label 属相。
