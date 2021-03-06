# link和@import引入样式的区别
### link🏷
```html
<link rel="stylesheet" type="text/css" href="目标文件的路径及文件名全称" />
```
> 使用link元素导入外部样式时，需将该元素写在文档头部(head里)
> rel：用于定义文档类型
> type：定义文档类型
### @import url()
```html
<style type="text/css">
			@import  url("目标文件的路径及文件名全称");
</style>
```
!> @和import之间没有空格，url和括号之间也没有空格，括号内部加引号，结尾必须以分号结束

### link和@import的区别
1. 语法归属：link属于`XHTML`标签，而@import是`CSS`提供的一种方式，link除了可以加载CSS外，还可以做很多其它的事情，比如定义RSS，定义rel连接属性等，@import就只能加载CSS

2. 加载顺序：一个页面被加载的时候，[link引用](/html/src和href属性的区别)的CSS会`同时加载`，而@import引用的CSS会等到页面全部下载完再加载，所以有时候浏览网页时一开始会没有样式

3. 兼容性：@import是`CSS2.1`提出的，只有在`IE5`以上的浏览器才能识别，link标签无此问题

4. 灵活性：当用`js`控制DOM去改变样式的时候，只能使用link标签，因为@import不是JS可以控制的
