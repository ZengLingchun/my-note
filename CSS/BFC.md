**BFC是什么**
> BFC块级格式上下文（block formating context），BFC是W3C CSS2.1规范中的一个概念，它决定了元素如何对其内容进行定位以及与其他元素的关系和相互作用。当一个使用了BFC时，它不会影响其他元素的的布局。

**如何触发BFC**

- body元素
- `flot`值不为`none`
- `position`为`absolute`或`fixed`
- `display`的值为`flex`，`grid`，`table-cell`
- 具有`overflow`且值不为`visible`的块级元素

**BFC可以解决的问题**

- 清除浮动
- 外边距重叠问题
- 自适应两列布局（`flot` + `overflow`）


