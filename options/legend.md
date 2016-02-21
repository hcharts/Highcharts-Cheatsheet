# legend
#### 图例说明是包含图表中数列标志或名称的容器。

```
legend: {
      align: 'center',           // 图例容器（中的图例）水平对齐在图表区，合法值有"left", "center" 和 "right". 默认是： center。
      backgroundColor: null,     // 图例容器的背景颜色。
      borderColor: '#909090',    // 图例容器的边框颜色。
      borderRadius: 0,           // 图例容器的边框圆角是否为圆角，默认值为0。
      borderWidth: 0,            // 图例容器的边框宽度，默认值为0。
      enabled: true,             // 显示或者隐藏图例使能。
      floating: false,           // 图例容器浮动使能。当此值被设置为true，数据图区域可以和图例容器重叠，并至于图例容器之下。
      itemDistance: 20,          // 当图例容器中的图例是水平布局时，这个属性定义了它们之间的距离，单位为像素，默认是： 20.
      itemHiddenStyle: null,     // 当点击图例进行隐藏时，CSS样式可以应用到图例容器中每个图例，它仅支持部分CSS，尤其对于文本样式，style内容能被很好的继承除非要重写，默认样式：itemHiddenStyle: { color: '#CCC' }
      itemHoverStyle: null,      // 图例悬浮时的样式，它仅支持部分CSS，尤其对于文本样式，style内容能被很好的继承除非要重写，默认: itemHoverStyle: { color: '#000' }
      itemMarginBottom: 0,       // 图例的每一项的底部外边距，单位px，默认值：0
      itemMarginTop: 0,          // 图例的每一项的顶部外边距，单位px，默认值：0
      itemStyle: { "color": "#333333", "cursor": "pointer", "fontSize": "12px", "fontWeight": "bold" },  // 每个图例项的样式，默认：itemStyle: { cursor: 'pointer', color: '#3E576F' }
      itemWidth: null,           // 每个图例项的宽度。当图例有很多图例项，并且用户想要这些图例项在同一平面内垂直对齐， 此时这个属性可帮用户实现此效果。
      labelFormat: '{name}',     // 每个图例标签的格式化字符串。此属性可引用在数列或者饼图节点对象中变量。
      labelFormatter: null,      // 每个图例标签的格式化的回调函数。这个this.关键字是指series对象(的属性),或者是饼图扇形数据节点。默认的是series或者数据列的name属性将被输出。
      layout: 'horizontal',      // 图例数据项的布局。布局类型：水平或垂直。默认是：水平
      lineHeight: 16,            // 图例项行高。2.1版本后已经废弃，取而代之的是可在itemStyle设置行高。 图例各项行高和内边距可用itemMarginTop 和 itemMarginBottom来设置。默认是：16.单位：px
      margin: 15,                // 整个图例区的外边距。如果整个图型区的大小是自动计算得出并且图例不浮动，那么图例边距的空间是指整个图例与坐标轴标签或者图形区之间的距离。默认值是：15
      maxHeight: null,           // 图例的最大高度。当超出最大高度，此时导航将显示。
      navigation: {
        activeColor: '#3E576F',  // 激活(箭头)颜色。在图例的导航页，激活的上箭头或者下箭头颜色。默认是： #3E576F.
        animation: true,         // 当点击图例的导航上下按钮时，触发的动画效果。默认的情况此属性设置为true， 额外的属性设置可封装在对象中，此对象包含easing 和 duration。默认是： true
        arrowSize: 12,           // 图例导航按钮的大小，默认是： 12.单位像素
        inactiveColor: '#CCC',   // 图例导航按钮未激活颜色。默认是： #CCC.
        style: null              // 图例导航文本样式。
      },
      padding: 8,        // 内边距
      reversed: false,   // 倒转。默认是： false.
      rtl: false,        // 图例符号是否在文本右边。默认是： false.
      shadow: false,     // 图例投影。当（用户想）应用投影到图例中时，只有backgroundColor也得应用到图例中，投影的效果才能生效。自2.3版本以后阴影能作为一个对象来配置，里面的属性有color, offsetX, offsetY, opacity 和 width. 默认是： false.
      symbolHeight: 12,  // 图标(图例中的符号)高度。默认是： 12.
      symbolPadding: 5,  // 图标和图例中的文本之间的距离。默认是： 5.单位：px
      symbolRadius: 2,   // 当图例是用矩形包裹时，图标的边框半径。默认是： 2.
      symbolWidth: 16,   // 图标宽度。默认是： 16. 单位：px
      title: {
        style: null,     // Generic CSS styles for the legend title.
        text: null       // A text or HTML string for the title.
      },
      useHTML: false,           // Whether to use HTML to render the legend item texts. When using HTML, legend.navigation is disabled.
      verticalAlign: 'bottom',  // The vertical alignment of the legend box. Can be one of "top", "middle" or "bottom". Vertical position can be further determined by the y option.
      width: null,              // The width of the legend box.
      x: 0,                     // The x offset of the legend relative to it's horizontal alignment align within chart.spacingLeft and chart.spacingRight. Negative x moves it to the left, positive x moves it to the right.
      y: 0                      // The vertical offset of the legend relative to it's vertical alignment verticalAlign within chart.spacingTop and chart.spacingBottom. Negative y moves it up, positive y moves it down.
}
```