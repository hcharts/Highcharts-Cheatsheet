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
        click: null,      // 单击数据区域(数据点以外)时触发。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
        drilldown: null,  // 单击钻取点后、新的数据列被增加前触发。 事件回调参数包括：point 表示引发钻取操作的点；seriesOptions 表示包含新数据列相关信息的对象。
        drillup: null,    // 从钻取后数据列上钻返回时触发。
        load: null,       // 图表加载完成时触发。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
        redraw: null,     // 图表重绘时触发。两种情况会触发重绘：调用 `chart.redraw()` 后；调用修改坐标轴、数据列或点的方法时，参数 redraw 设置为 true 。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
        selection: null   // 图表区域被选中时触发。设置 zoomType 属性可开启选取功能。`this` 关键字指向 chart 对象自身，唯一参数 event 被传入回调函数。
      },
      height: null,              // 明确指定图表高度。默认情况下，图表高度通过容器元素高度的 offset 值计算而来，如果容器元素高度为 0 ，则图表高度默认为 400 像素。
      ignoreHiddenSeries: true,  // 若为 true ，当隐藏某数据列时，坐标轴将根据剩下的可视数据列进行缩放。
      inverted: false,           // 是否反转坐标轴，这样一来可以使 x 轴在垂直方向， y 轴在水平方向。设置为 true 时，x 轴一般情况下会反转，而条形图(bar图)是自动反转的。
      margin: [null],            // 图表外边框与图形区域之间的 margin 距离，值为数组。数组中各值表示上、右、下、左的 margin 值，也可以使用 marginTop、marginRight、marginBottom、marginLeft 单独设置。
      marginBottom: null,        // The margin between the bottom outer edge of the chart and the plot area. Use this to set a fixed pixel value for the margin as opposed to the default dynamic margin.
      marginLeft: null,          // The margin between the left outer edge of the chart and the plot area. Use this to set a fixed pixel value for the margin as opposed to the default dynamic margin.
      marginRight: null,         // The margin between the right outer edge of the chart and the plot area. Use this to set a fixed pixel value for the margin as opposed to the default dynamic margin.
      marginTop: null,           // The margin between the top outer edge of the chart and the plot area. Use this to set a fixed pixel value for the margin as opposed to the default dynamic margin.
      options3d: {
        alpha: 0,        // One of the two rotation angles for the chart.
        beta: 0,         // One of the two rotation angles for the chart.
        depth: 100,      // The total depth of the chart.
        enabled: false,  // Wether to render the chart using the 3D functionality.
        frame: {
          back: {
            color: transparent,   // The color of the panel.
            size: 1               // Thickness of the panel.
          },
          bottom: {
            color: transparent,   // The color of the panel.
            size: 1               // Thickness of the panel.
          },
          side: {
            color: transparent,   // The color of the panel.
            size: 1               // Thickness of the panel.
          }
        },
        viewDistance: 100         // Defines the distance the viewer is standing in front of the chart, this setting is important to calculate the perspective effect in column and scatter charts. It is not used for 3D pie charts.
      },
      pinchType: null,            // Equivalent to zoomType, but for multitouch gestures only. By default, the pinchType is the same as the zoomType setting.
      plotBackgroundColor: null,  // The background color or gradient for the plot area.
      plotBackgroundImage: null,  // The URL for an image to use as the plot background.
      plotBorderColor: '#C0C0C0', // The color of the inner chart or plot area border.
      plotBorderWidth: 0,         // The pixel width of the plot area border.
      plotShadow: false,          // Whether to apply a drop shadow to the plot area.
      polar: false,               // When true, cartesian charts like line, spline, area and column are transformed into the polar coordinate system.
      reflow: true,               // Whether to reflow the chart to fit the width of the container div on resizing the window.
      renderTo: null,             // The HTML element where the chart will be rendered. If it is a string, the element by that id is used. The HTML element can also be passed by direct reference.
      resetZoomButton: {
        position: null,           // The position of the button. This is an object that can hold the properties align, verticalAlign, x and y.
        relativeTo: 'plot',       // What frame the button should be placed related to. Can be either "plot" or "chart".
        theme: null               // A collection of attributes for the button. The object takes SVG attributes like fill, stroke, stroke-width or r, the border radius.
      },
      selectionMarkerFill: rgba(69,114,167,0.25),  // The background color of the marker square when selecting (zooming in on) an area of the chart.
      shadow: false,                               // Whether to apply a drop shadow to the outer chart area. Requires that backgroundColor be set. Since 2.3 the shadow can be an object configuration containing color, offsetX, offsetY, opacity and width.
      showAxes: false,                             // Whether to show the axes initially. This only applies to empty charts where series are added dynamically, as axes are automatically added to cartesian series.
      spacing: [10, 10, 15, 10],                   // The distance between the outer edge of the chart and the content, like title, legend, axis title or labels. The numbers in the array designate top, right, bottom and left respectively.
      spacingBottom: 15,                           // The space between the bottom edge of the chart and the content (plot area, axis title and labels, title, subtitle or legend in top position).
      spacingLeft: 10,                             // The space between the left edge of the chart and the content (plot area, axis title and labels, title, subtitle or legend in top position).
      spacingRight: 10,                            // The space between the right edge of the chart and the content (plot area, axis title and labels, title, subtitle or legend in top position).
      spacingTop: 10,                              // The space between the top edge of the chart and the content (plot area, axis title and labels, title, subtitle or legend in top position).
      style: null,                                 // Additional CSS styles to apply inline to the container div. Note that since the default font styles are applied in the renderer, it is ignorant of the individual chart options and must be set globally.
      type: 'line',                                // 图表默认的数据列类型，可以是 plotOptions 列表中的任一类型。
      width: null,                                 // An explicit width for the chart. By default the width is calculated from the offset width of the containing element.
      zoomType: null,                              // Decides in what dimentions the user can zoom by dragging the mouse. Can be one of x, y or xy.

    }
````