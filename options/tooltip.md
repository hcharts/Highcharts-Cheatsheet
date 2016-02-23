# tooltip

### 数据提示框

当鼠标悬停在某点上时，以框的形式提示该点的数据，比如该点的值，数据单位等。数据提示框内提示的信息完全可以通过格式化函数动态指定。

```js
tooltip: {
  animation: true,                             // 启用或禁用提示框的动画效果。在旧版本 IE 浏览器中，动画效果默认被禁用。
  backgroundColor: rgba(255, 255, 255, 0.85),  // 提示框的背景色或渐变。
  borderColor: 'auto',                         // 提示框的边框颜色。为 null 时， 边框将采用数据列或点的颜色。
  borderRadius: 3,                             // 提示框的圆角边框值。
  borderWidth: 1,                              // 提示框的边框宽度像素值。
  crosshairs: null,                            // 十字准线。十字准线可以被定义为布尔值、布尔值构成的数组，或对象。
  dateTimeLabelFormats: {                      // 数据列的坐标轴为 `datetime`时使用。默认日期格式通过最近的数据点推测。以下示例各时间单位的默认字符串描述格式，更多内容参见 dateFormat 。
    millisecond: '%A, %b %e, %H:%M:%S.%L',
    second: '%A, %b %e, %H:%M:%S',
    minute: '%A, %b %e, %H:%M',
    hour: '%A, %b %e, %H:%M',
    day: '%A, %b %e, %Y',
    week: 'Week from %A, %b %e, %Y',
    month: '%B %Y', year:'%Y'
  },
  enabled: true,           // 启用或禁用提示框。
  followPointer: false,    // 鼠标滑过柱状图各列、饼图各分片等，提示框是否跟随鼠标平滑移动。默认情况下，散点图、气泡图和饼图的提示框会跟随鼠标移动，这是通过 plotOptions 覆盖相应的属性实现的。
  followTouchMove: false,  // 触摸屏上，提示框是否跟随手指移动。默认值 false 是出于这样一种考虑：多数触摸屏上滑动手指的默认动作是滚动 web 页面。设置为 true 后，用户在图表内滑动手指将不能滚动页面，这会造成用户的困惑，因此需谨慎设置该值。
  footerFormat: false,     // 数据提示框尾部的 HTML 格式化字符。
  formatter: null,         // 用于格式化提示框文本的回调函数。回调函数返回 false 以禁用特定点的提示框。
  headerFormat: '<span style="font-size: 10px">{point.key}</span><br/>',  // 数据提示框头部的 HTML 格式化字符。变量通过花括号包裹，可用变量有 point.key、series.name、series.color 以及其它 point、series 对象上的属性。根据坐标轴的类型不同，point.key 变量包含了 category 名， x 值或 datetime 字符串。对于 datetime 类型的坐标轴，point.key 的日期格式可以用 tooltip.xDateFormat 设置。
  hideDelay: 500,          // The number of milliseconds to wait until the tooltip is hidden when mouse out from a point or chart.
  pointFormat: '<span style="color:{series.color}">\u25CF</span> {series.name}: <b>{point.y}</b><br/>',  // The HTML of the point's line in the tooltip. Variables are enclosed by curly brackets. Available variables are point.x, point.y, series.name and series.color and other properties on the same form. Furthermore, point.y can be extended by the tooltip.yPrefix and tooltip.ySuffix variables.
  positioner: null,        // A callback function to place the tooltip in a default position. The callback receives three parameters: labelWidth, labelHeight and point, where point contains values for plotX and plotY telling where the reference point is in the plot area. Add chart.plotLeft and chart.plotTop to get the full coordinates.
  shadow: true,            // Whether to apply a drop shadow to the tooltip.
  shape: 'callout',        // The name of a symbol to use for the border around the tooltip. In Highcharts 3.x and less, the shape was square.
  shared: false,           // When the tooltip is shared, the entire plot area will capture mouse movement. Tooltip texts for series types with ordered data (not pie, scatter, flags etc) will be shown in a single bubble. This is recommended for single series charts and for tablet/mobile optimized charts.
  snap: null,              // Proximity snap for graphs or single points. Does not apply to bars, columns and pie slices. It defaults to 10 for mouse-powered devices and 25 for touch devices.
  style: null,             // CSS styles for the tooltip. The tooltip can also be styled through the CSS class .highcharts-tooltip.
  useHTML: false,          // Use HTML to render the contents of the tooltip instead of SVG. Using HTML allows advanced formatting like tables and images in the tooltip. It is also recommended for rtl languages as it works around rtl bugs in early Firefox.
  valueDecimals: null,     // How many decimals to show in each series' y value. This is overridable in each series' tooltip options object. The default is to preserve all decimals.
  valuePrefix: null,       // A string to prepend to each series' y value. Overridable in each series' tooltip options object.
  valueSuffix: null,       // A string to append to each series' y value. Overridable in each series' tooltip options object.
  xDateFormat: null        // The format for the date in the tooltip header if the X axis is a datetime axis. The default is a best guess based on the smallest distance between points in the chart.
}
```