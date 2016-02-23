# chart

### 关于图表区和图形区的参数及一般图表通用参数。

````js
chart: {
  alignTicks: true,           // 当使用多个轴时，两个或两个以上相反轴通过计算出合理的刻度间隔使刻度线数保持最少，并自动对齐到最少的刻度线上。
  animation: true,            // 设置所有图表在更新时的整体动画。设置该属性为 false 可以禁用图表动画。
  backgroundColor: '#FFF',    // 外图表区域的背景色或渐变。
  borderColor: '#4572A7',     // 外图表区域的边框颜色。
  borderRadius: 5,            // 外图表区域的圆角边框像素值。默认值为 5 ，导出时默认值为 0 。
  borderWidth: 0,             // 外图表区域的边框宽度像素值。
  className: null,            // 附加在图表容器 div 上的 CSS 样式名，可以给各个图表添加独立的样式。
  defaultSeriesType: 'line',  // type 属性的别名。
  events: {
    addSeries: null,  // 图表加载后，使用 addSeries 方法增加数据列时触发。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
    click: null,      // 单击图形区域(数据点以外)时触发。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
    drilldown: null,  // 单击钻取点后、新的数据列被增加前触发。事件回调参数包括：point 表示引发钻取操作的点；seriesOptions 表示包含新数据列相关信息的对象。
    drillup: null,    // 从钻取后的数据列上钻返回时触发。
    load: null,       // 图表加载完成时触发。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
    redraw: null,     // 图表重绘时触发。两种情况会触发重绘：调用 `chart.redraw()` 后；调用修改坐标轴、数据列或点的方法时，参数 redraw 设置为 true 。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
    selection: null   // 图表区域被选中时触发。设置 zoomType 属性可开启选取功能。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
  },
  height: null,              // 明确指定图表高度。默认情况下，图表高度通过容器元素高度的 offset 值计算而来，如果容器元素高度为 0 ，则图表高度默认为 400 像素。
  ignoreHiddenSeries: true,  // 若为 true ，当隐藏某数据列时，坐标轴将根据剩下的可视数据列进行缩放。
  inverted: false,           // 是否反转坐标轴，这样一来可以使 x 轴在垂直方向， y 轴在水平方向。设置为 true 时，x 轴一般情况下会反转，而条形图(bar图)是自动反转的。
  margin: [null],            // 图表外边框与图形区域之间的 margin 距离，值为数组。数组中各值表示上、右、下、左的 margin 值，也可以使用 marginTop、marginRight、marginBottom、marginLeft 单独设置。
  marginBottom: null,        // 图表底部外边框与图形区域之间的 margin 距离。设置为固定像素值以代替默认情况下动态计算的值。
  marginLeft: null,          // 图表左侧外边框与图形区域之间的 margin 距离。设置为固定像素值以代替默认情况下动态计算的值。
  marginRight: null,         // 图表右侧外边框与图形区域之间的 margin 距离。设置为固定像素值以代替默认情况下动态计算的值。
  marginTop: null,           // 图表顶部外边框与图形区域之间的 margin 距离。设置为固定像素值以代替默认情况下动态计算的值。
  options3d: {
    alpha: 0,        // 图表的两个旋转角度之一。
    beta: 0,         // 图表的两个旋转角度之一。
    depth: 100,      // 图表的总深度。 
    enabled: false,  // 是否启用3D函数渲染图表。
    frame: {
      back: {
        color: transparent,   // 面板颜色。
        size: 1               // 面板厚度。
      },
      bottom: {
        color: transparent,   // 面板颜色。
        size: 1               // 面板厚度。
      },
      side: {
        color: transparent,   // 面板颜色。
        size: 1               // 面板厚度。
      }
    },
    viewDistance: 100         // 观看者在图前的距离，该配置项在计算柱状图和散点图的透视效果时非常有用，不能用于3D饼图。
  },
  pinchType: null,            // 同 zoomType, 仅用于多点触控手势。默认值与 zoomType 相同。
  plotBackgroundColor: null,  // 图形区域的背景颜色或渐变。
  plotBackgroundImage: null,  // 图形区域背景图片的URL。
  plotBorderColor: '#C0C0C0', // 图表内边框或图形区域边框的颜色。
  plotBorderWidth: 0,         // 图形区域边框宽度，单位为像素。
  plotShadow: false,          // 图形区域是否使用阴影效果。
  polar: false,               // 设置为 true 时， 直线图、曲线图、面积图、柱状图等直角坐标图会被转到极坐标系中。
  reflow: true,               // 窗口大小改变时，图表是否进行浏览器回流以适应容器 div 的宽度。
  renderTo: null,             // 渲染图表用的 HTML 元素。如果是字符串，则代表该 HTML 元素的 id ，也可以传入元素的直接引用。
  resetZoomButton: {
    position: null,           // 按钮位置。它是一个对象，包含 align、verticalAlign、x 和 y 属性。
    relativeTo: 'plot',       // 按钮位置相对于谁。值可以是 "plot" 表示绘图区，或是 "chart" 表示整个图表区。
    theme: null               // 按钮主题，该对象是一个 SVG 属性集，例如 fill、stroke、stroke-width 或 r ，以及边框圆角等。
  },
  selectionMarkerFill: rgba(69,114,167,0.25),  // 选中图表某一区域进行放大时，该选区的背景色。
  shadow: false,                               // 外图表区域是否使用阴影效果，必须设置 backgroundColor 属性. 从 2.3 版本开始该值也可以为对象，包含 color、offsetX、offsetY、opacity 及 width 属性。
  showAxes: false,                             // 是否显示坐标轴。它只能用于数据列是动态增加的空图表，否则坐标轴会被自动添加。
  spacing: [10, 10, 15, 10],                   // 图表外边框与其内容（如标题、图例、坐标轴标题或标签）的距离，值为数组。数组中各值分别表示上、右、下、左。
  spacingBottom: 15,                           // 图表底部外边框与其内容（图形区域、坐标轴标题及标签、标题、子标题或图例）的距离。
  spacingLeft: 10,                             // 图表左侧外边框与其内容（图形区域、坐标轴标题及标签、标题、子标题或图例）的距离。
  spacingRight: 10,                            // 图表右侧外边框与其内容（图形区域、坐标轴标题及标签、标题、子标题或图例）的距离。
  spacingTop: 10,                              // 图表顶部外边框与其内容（图形区域、坐标轴标题及标签、标题、子标题或图例）的距离。
  style: null,                                 // 以内联方式附加至容器 div 的 CSS 样式。需要注意的是，默认的字体样式是由渲染器决定的，因而单独设置它并不明智，而应该进行全局设置。
  type: 'line',                                // 图表默认的数据列类型，可以是 plotOptions 列表中的任一类型。
  width: null,                                 // 明确指定图表宽度。默认情况下，图表宽度通过容器元素宽度的 offset 值计算而来。
  zoomType: null,                              // 用户拖动鼠标时，在哪个维度放大。可选的值为 x、y 或 xy 。
}
````