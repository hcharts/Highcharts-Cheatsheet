# series
#####对系列的参数配置。
#####2016-02-21 @webkong
```
series: {
  data: {
    color: null,        // 对点设置单独的颜色。默认的颜色是从全局的颜色数组中获取。
    dataLabels: null,   // 对点设置单独的数据标签（data label）。该配置项和plotOptions.series.dataLabels功能一致。
    drilldown: null,    // 设置该点下钻的id，id对应 drilldown.series 数组中的某个系列。
    events: {
      click: null,      // point点击时触发。this关键字指点对象本身。event作为参数传递给函数。event参数包含了Hchart开发基础库jQuery和MooTools的公共事件。
      mouseOut: null,   // 当鼠标移出时触发。this关键字指移出点对象本身。event作为参数传递给函数。event参数包含了Hchart开发基础库jQuery和MooTools的公共事件。
      mouseOver: null,  // 当鼠标移入时触发。this关键字指移入点对象本身。event作为参数传递给函数。event参数包含了Hchart开发基础库jQuery和MooTools的公共事件。
      remove: null,     // 当某点用 .remove() 方法移除时触发。this关键字指移除点对象本身。event作为参数传递给函数。 当返回 false 时取消移除操作。
      select: null,     // 当通过程序或者点击事件选中时触发。this关键字指选中点对象本身。event作为参数传递给函数。 当返回 false 时取消选中操作。
      unselect: null,   // 当通过程序或者点击事件取消选中时触发。this关键字指取消选中的点对象本身。event作为参数传递给函数。 当返回 false 时取消选中操作。
      update: null      // 当通过程序或者 .update() 对象更新时触发。this关键字指更新点对象本身。event作为参数传递给函数。 更新点通过 event.options 设置. 当返回 false 时取消更新操作。
    },
    id: null,                  // 点的id。id可以通过 chart.get() 方法，在图表渲染后获得一个指向该id的点的指针。
    isIntermediateSum: false,  // 仅用于瀑布系列图表（Waterfall series）. 当这个属性设置为true时，该点作为汇总列，添加或减去自上次中间汇总列的值，或自开始汇总的值。配置的y的值将被忽略。
    isSum: false,              // 仅用于瀑布系列图表（Waterfall series）. 这个属性设置为true时，该点显示整个系列的汇总. 配置的y的值将被忽略。
    legendIndex: null,         // 仅用于饼状图. 饼图切片的图例索引顺序。
    marker: {
      enabled: true,         // 启用或者禁用点（标记）.
      fillColor: null,       // 点（标记）的填充颜色。如果是null，则使用系列或者点的颜色。
      lineColor: '#FFFFFF',  // 点（标记）的边框颜色. 如果是null，则使用系列或者点的颜色。
      lineWidth: 0,          // 点（标记）的边框宽度。
      radius: 4,             // 点（标记）的半径.
      states: {
        hover: {
          enabled: true,         // 启用或者禁用点（标记）的hover状态.
          fillColor: null,       // hover状态时，点（标记）的填充颜色。
          lineColor: '#FFFFFF',  // hover状态时，点（标记）的边框颜色. 如果是null，则使用系列或者点的颜色。
          lineWidth: 0,          // hover状态时，点（标记）的边框宽度。
          radius: null           // 点（标记）的半径。hover状态时, 默认值是 正常状态的值 +2。
        },
        select: {
          enabled: true,         // 启用或者禁用点（标记）的选中状态.
          fillColor: null,       // 选中状态时，点（标记）的填充颜色。
          lineColor: '#FFFFFF',  // 选中状态时，点（标记）的边框颜色. 如果是null，则使用系列或者点的颜色。
          lineWidth: 0,          // 选中状态时，点（标记）的边框宽度。
          radius: null           // 点（标记）的半径。选中状态时, 默认值是 正常状态的值 +2。
        }
      },
      symbol: null    // 点（标记）的预定义形状或符号。为空的时候， 符号从 options.symbols 配置中获取值.其他可用的值为"circle", "square", "diamond", "triangle" and "triangle-down"（圆形、正方形、菱形、三角形、倒三角形）.
    },
    name: null,       // 在图例、提示框、数据标签等中显示的名字。
    sliced: false,    // 仅饼状图使用。是否对于中心显示一个偏移距。
    x: null,          // 点 x轴的值.
    y: null           // 点 y轴的值.
  },
  id: null,           // 点的id。id可以通过 chart.get() 方法，在图表渲染后获得一个指向该id系列对象的指针。
  index: null,        // 系列（series）在图表中的索引，影响 chart.series 数组中的内部索引, 也会影响图例的显示顺序。
  legendIndex: null,  // 图例显示的顺序索引. 译注：优先级大于index的影响顺序
  name: null,         // 在图例、提示等显示的名字。
  stack: null,        // 允许在堆叠图中进行分组。选项可以是一个字符串或一个数字或其它任何东西，只要分组系列的堆栈选项互相匹配。
  type: null,         // 系列的类型。可以是 area, areaspline, bar, column, line, pie, scatter or spline. 从2.3版本开始支持arearange、areasplinerange和columnrange 类型，但需提前加载 highcharts-more.js 组件使用。
  xAxis: 0,           // 当使用双重或者多重x轴时，通过id或者index来关联系列对应的x轴。默认为0
  yAxis: 0,           // 当使用双重或者多重y轴时，通过id或者index来关联系列对应的y轴。默认为0
  zIndex: null,       // 定义系列的画面层次。
},
```
