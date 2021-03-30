### 用边框画三角形
``` css
.box{
  border: 10px solid;
  width: 0;
 ​ border: red	transparent	transparent	transparent;
}
```
### 文本溢出显示省略号
**overflow**
> `visible`:默认值，内容不会被修剪，会呈现在元素框之外<br>
> `hidden`：内容会被修剪，并且其余内容是不可见的；<br>
> `scroll`：内容会被修剪，但是浏览器会显示滚动条，以便查看其余的内容;<br>
> `auto`：如果内容被修剪，则浏览器会显示滚动条，以便查看其他的内容;<br>
> `inherit`：规定应该从父元素继承overflow属性的值。

**white-space**
> `normal`：默认值，多余空白会被浏览器忽略只保留一个；<br>
> `pre`：空白会被浏览器保留；<br>
> `pre-wrap`：保留一部分空白符序列，但是正常的进行换行；<br>
> `pre-line`:合并空白符序列，但是保留换行符；<br>
> `nowrap`:文本不会换行，文本会在同一行上继续，直到遇到br标签为止;

**text-overflow**
> `clip`：不显示省略号（...），而是简单的裁切<br>
> `ellipsis`：当对象内文本溢出时，显示省略标记

**文本溢出设置省略号**
> 1. 容器宽度：`width`：value；（px、%，都可以）
> 2. 强制文本在一行内显示:`white-space`：nowrap;
> 3. 溢出内容为隐藏：`overflow`：hidden；
> 4. 溢出文本显示省略号：`text-overflow`：ellipsis;
> 5. 如果为多行文本，还需加上`-webkit-line-clamp`: 2;(显示的`行数`)

```css
例子：🌰
p{
​ width: 300px;
​ display: -webkit-box;
​ -webkit-box-orient:vertical;
​ -webkit-line-clamp: 2;
​ overflow: hidden;
​ }
```
