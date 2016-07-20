#### 2、背景与边框
##### 半透明边框
半透明的边框默认会被背景剪裁掉，需要设置`background-clip:padding-box;`，这样浏览器会用内边距的边沿把背景剪裁掉。
PS:默认背景`background-clip:border-box;`

##### 多重边框
1) 使用`box-shadow`实现多个投影边框背景的重叠显示，只能产生实线边框：

* 投影行为跟边框不完全一致，因为它不会影响布局，而且也不会收到box-sizing属性的影响。
* 投影产生的边框并不会响应鼠标事件，比如悬停或点击。

2) 使用`outline`描边产生外层边框，可以产生虚线等样式

* outline只适用于产生双层“边缘”的场景，它不能接受用逗号分隔的多个值。
* 边框不一定会贴合border-radius属性产生的圆角。如果元素是圆角的，描边还是直角的（未来可能有变化）

##### 灵活的背景定位
1) 使用background-position扩展语法
`background-position:right 20px bottom 10px;`
为了兼容可以在background中使用一个回退方案：将之前的定位写在background中
2) 使用background-origin方案
在给背景图片设置距离某个角的偏移量时，有一种情况极其常见：偏移量与容器的内边距一致。这时候可以使用`background-origin`自动跟着设定的内边距走，不用另外声明偏移量的值。
