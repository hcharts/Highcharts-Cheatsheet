# subtitle & title
##### 图标的标题和副标题
##### 2016-02-22 @webkong
```
//副标题
subtitle: {
  align: 'center',                // 文本水平对齐方式。可选“left”，”center“和“right”。
  floating: false,                // 是否浮动，如果设置为浮动，副标题将不占用图表区的位置。
  style: { 'color': '#555555' },  // 文字样式。用于设置文字颜色、字体、字号。精确定位，可以更改margin属性、添加position："absolute"、或者修改left 和 top 属性值。
  text: null,                     // 图表的副标题文字，默认是空。
  useHTML: false,                 // 副标题是否使用HTML渲染，设置解析后，可以使用例如 a 等html标签。
  verticalAlign: null,            // 文字垂直对齐方式。可选“top”，”middle“和“bottom”。当给定一个值时，标题将表现为浮动。
  x: 0,                           // 相对于水平对齐的偏移量，取值范围：图表左边距到图表右边距，可以是负值，单位px。
  y: null                         // 相对于垂直对齐的偏移量，取值范围：图表的上边距到图表的下边距，可以是负值，单位是px。一般情况下副标题默认是在标题下面的，除非标题是floating属性。
},
//标题
title: {
  align: 'center',                                    // 图表标题水平对齐方式。有“"left", "center" and "right"可选，分别对应“左对齐”、“居中对齐”、“右对齐”。
  floating: false,                                    // 标题是否浮动。当设置为true，标题将不占空间。
  margin: 15,                                         // 标题和图表区的间隔。当有副标题，表示标题和副标题之间的间隔。
  style: { 'color': '#333333', 'fontSize': '18px' },  // 标题样式。用于设置文字颜色、字体、字号，但是字体的对齐则使用algin、x和y元素。
  text: 'Chart title',                                // 图表的标题名，如果想不显示标题，把text设置为null。
  useHTML: false,                                     // 副标题是否使用HTML渲染，设置解析后，可以使用例如 a 等html标签。
  verticalAlign: null,                                // 标题垂直对齐方式。有“top”，”middle“和“bottom” 可选，分别对应“顶对齐”、“居中对齐”、“底对齐”。当给定一个值时，该标题将表现为浮动。
  x: 0,                                               // 相对于水平对齐的偏移量，取值范围：图表左边距到图表右边距，可以是负值，单位px。
  y: 15                                               // 相对于垂直对齐的偏移量，取值范围：图表的上边距到图表的下边距，可以是负值，单位是px。 译注：默认值会取决于设置的字体大小。
},
```
