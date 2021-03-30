### 什么是BFC？
?> `BFC(block formatting context)`直译为`块级格式化上下文`。它是一个独立的渲染区域，只有`Blovk-level box`参与，它规定了内部的box如何布局，并且这个区域与外部毫不相干

### BFC的布局规则

1. 内部的Box会在`垂直方向`，一个接一个的放置

2. Box垂直方向的距离由`margin`决定，属于同一个BFC的两个`相邻Box`的margin会发生重叠(取最大的margin值)

3. 每个元素的`margin-left`的左边会与包含块的`border-left`相接触

4. BFC的区域不会与`float-box`重叠

5. BFC就是页面上的一个隔离的`独立容器`，容器里的子元素不会影响到外面的元素

6. 计算BFC的高度时，浮动元素也参与计算

> **普通文档流布局规则**<br>
> 1. 浮动的元素是不会被父级计算高度<br>
> 2. 非浮动元素会覆盖浮动元素的位置<br>
> 3. margin会传递给父级<br>
> 4. 两个相邻元素上下margin会重叠

### 触发BFC的条件
1. 根元素(`html`)

2. `float`属性不为`none`

3. `position`为`absolute`或`fixed`

4. `display`为`inline-block`,`table-cell`,`table-caption`,`flex`,`inline-flex`

5. `overflow`不为`visible`

### BFC的应用
1. 自适应两栏布局

2. [清除内部浮动](/css/清除浮动的方法合集)

3. 放置margin上下重叠
