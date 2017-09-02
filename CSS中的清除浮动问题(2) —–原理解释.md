#### 关于浮动的问题就涉及到了一个BFC的概念（Block Formating Context 块级格式上下文），只有块盒子参与。符合以下的其中之一就会创建一个BFC

- 根元素（默认就是一个BFC）
- float除了none的其它属性
- position除了relative和statisc的其他属性
- overflow除了visible
- dispaly为inline-block table-cell table-caption

上一篇中通过加overflow：hidden来消除浮动的原理就是在父元素创建一个BFC，因为“计算BFC的高度时，会将子元素的浮动高度计算进去”，所以就不会造成父元素不加高度时子元素加浮动造成的高度倒塌（其实除了加overflow：hidden来创建BFC还可以通过上面的几个之一创建BFC，根据实际）

PS：在一个BFC内部如果有一个新的BFC并且存在内部元素是浮动元素，则该BFC区域不会和浮动元素重叠

