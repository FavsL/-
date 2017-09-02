###css中浮动问题是一个很重要的东西，很多时候我们需要通过清除浮动来保持页面的一致性。一般有3种清楚方法

overflow:hidden   这种方法在父元素中应用，但是弊端是会使得超出元素范围的部分强行被隐藏
 通过在浮动元素后建立一个空的div设置样式{ clear：both}来清除，但是会增加很多无用的div标签
最佳方法，利用伪元素来消除，可大大减少css代码
demo:
```html
<style type="text/css">
.clearfix {*zoom: 1;}
.clearfix::after
{clear:both;                       /*最推荐的清除浮动的方法*/
content: "";                         
display: block;                                      
height: 0;
visibility: hidden;
}
#wrapper
{
width: 200px;
border: 1px solid black;
}
#first,#second
{
width: 80px;
height: 40px;
border: 1px solid red;
}
#first {float: left;}
#second {float: right;}
</style>
	

<div id="wrapper" class="clearfix">
	<div id="first"></div>
	<div id="second"></div>
</div>
```

通过在定义一个公有类clearfix，在需要消除浮动影响的父元素中添加这个公有类就可以了
