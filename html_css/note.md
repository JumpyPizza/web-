# HTML&CSS 学习笔记
## HTML  
HTML也叫作超文本标记语言。在网页最开始要声明<!DOCTYPE html>，所以可以认为html是一种文档类型，html文档。  
### HEAD
\<h>标签通常用来表示题目，从\<h1>开始,结束之后要加上结束标签，由转义斜杠的反斜杠加标签组成\</h1> HEAD  
### Paragraph
\<p>标签就是段落标签。 标题标签带序号，因为有一级标题、二级标题... Paragraph  
注释： 由\<!--开始，-->结束  
### properties 
和XML一样，标签可以带有属性，比如设置标题的颜色：\<h1 style='color: blue'> 在开始标签后面就是属性的类别，为类别赋予一个值。 这个叫元素的样式，style是一个inline style，另外一种添加样式的方法是CSS。标签声明多个class属性，在同一个class中用空格隔开：class='class1 class2'  
### CSS
CSS可以通过\<style>标签使用，在标签里，缩进一个tab，加入： `选择器{属性名称:属性值;}`，比如：`h2 {color:red;}`  每个花括号中写完属性值后用**;**结尾
**在CSS中，还可以定义类！**在\<style>标签中，在原来选择器的位置使用.name创建类名，后面{}填入属性，然后在标签中使用class=name，就可以为标签添加这个样式。
通过\<img src=''>来引入图片，这是一个自关闭标签。img标签具有alt属性
### 锚点元素 a
\<a href=''>文字</a>
### 列表
\<ul>开始，unordered list；\<ol>开始，ordered list；中间的元素为\<li>
### 文本输入框
\<input type='text'>这是一个**自关闭标签**，可以加上一个预设值：\<input type='text' placeholder='预设值'>，可以加上required属性，规定这个表单必须提交
可以将输入框嵌套在表单\<form>元素中，\<form action='提交表单的地址'>
在输入框后加入button标签：\<button type='submit'>文本</button>，创造一个`文本`按钮，将数据提交到action里的地址
### 单选按钮、复选框
单选框也用\<input>标签，其属性type='radio'，单选框的input必须放在\<label>标签中，有一个name属性，所有关联的单选按钮的name应相同。  
\<label>  
    \<input type='radio' name='name'>  
    按钮文字  
\</label>  
复选框与单选按钮差不多，type='checkbox'  
在它们的input属性里加入checked，可以设置预选  
### div
div元素全称division，层的意思，是元素的容器。为某个div应用的style可以应用到其中的所有元素，比如\<div class=***class defined before in style***>
### id
可以在定义style的时候，用#id定义一个id选择器
### margin padding
对于一个有border属性的元素来说，margin是外边距，padding是内边距。  
CSS的继承：
```
<style>

.box {
border-style: solid;
border-color: black;
border-width: 5px;
text-align: center;
}

.yellow-box {
background-color: yellow;
padding: 10px;
}
</style>

.red-box {
background-color: red;
padding: 20px;
margin: -15px;
}

<div class="box yellow-box">
<h5 class="box red-box">padding</h5>
</div>

```
先定义了一个box类的边框，继承box的就有了这些边框的属性，同时又有自己的颜色、边距属性。在\<div>中使用yellow-box，则将div这一层里的元素都放在黄框中。

