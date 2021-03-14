一、伪类和伪元素的区别

伪类用“:”表示，伪元素用“::”表示。区别是，当实现时，需要新增元素的就是伪类，需要新增元素的就是伪元素

二、margin重叠问题

相邻的两个dom元素的margin会重叠。即子元素的margin也会影响父元素的margin重叠。

解决：变成BFC模式或为子元素添加padding

三、层叠上下文

每个元素都有自己的层叠上下文，顺序：background -> -z-index -> block -> float -> inline-block -> z-index:atuo -> z-index
