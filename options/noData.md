# noData
##### 用于设置显示一条类似“没有要显示的数据”的选项，这个特性需要在页面头部加载no-data-to-display.js文件，要显示的文本内容是在 lang.noData 设置的
#####2016-02-19 @webkong

```
noData: {
  attr: null,                                                                  // 无数据标签中额外的SVG属性.
  position: { 'x': 0, 'y': 0, 'align': 'center', 'verticalAlign': 'middle' },  // 设置相对于绘图区，无数据标签的位置
  style: { "fontSize": "12px", "fontWeight": "bold", "color": "#60606a" }      // 设置无数据标签的CSS样式
},
```
