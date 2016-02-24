# exporting

###图表输出功能模块，这里输出包括导出(export)和打印(print)。

```js
exporting: {
      buttons: {                  //导出或者打印相关按钮的设置。
        contextButton: {          //输出按钮选项
          align: 'right',         // 按钮的对齐方式，默认是 "right"。
          enabled: true,          // 是否启用导出按钮。
          height: 20,             // 按钮的高度(单位:px)。默认是：20。
          menuItems: null,        // 菜单项目的配置选项对象集。每个选项对象包含一个文本选项和一个onclick回调函数，文本选项用于设置弹出框出现时显现的文字，回调函数在对应菜单项被点击时触发。默认是：null。
          onclick: null,          // 按钮被点击时触发的回调函数。默认是：null。
          symbol: 'menu',         // 按钮的符号。 指向Highcharts.Renderer.symbols集合中的定义函数。默认的exportIcon函数是导出模块的一部分。默认是 "menu"。
          symbolFill: '#A8BF77',  // 符号填充色，见 navigation.buttonOptions => symbolFill. 默认是： #A8BF77。
          symbolSize: 14,         // 符号大小，单位：px。默认是： 14。
          symbolStroke: '#666',   // 符号描边色。默认是： #666。
          symbolStrokeWidth: 1,   // 符号描边宽度，单位px。默认是：1。
          symbolX: 12.5,          // 符号中心点x轴坐标，默认是：12.5。
          symbolY: 10.5,          // 符号中心点y轴坐标，默认是：10.5。
          text: null,             // 为按钮添加文字，默认是：null。
          theme: null,            // 按钮主题的配置对象。 该对象可使用SVG属性，如stroke-width、stroke和fill。默认是：null。
          verticalAlign: 'top',   // 按钮在垂直方向上的对齐方式。 可选值为 "top"、"middle"或者 "bottom"。默认是：top。
          width: 24,              // 按钮的宽度，单位：px。默认值是：24。
          x: -10,                 // 按钮在水平方向上相对于align的偏移量。默认是： -10。
          y: 0                    // 按钮在垂直方向上相对于verticalAlign的偏移量。默认是： 0。
        }
      },
      chartOptions: null,                   // 对导出后的图表进行额外的属性设置。 例如， 可以对导出的图片设置合适的宽度和高度，或者更好的配色方案。默认值是：null。
      enabled: true,                        // 是否启用导出功能模块。不启用导出功能将隐藏导出按钮，但API方法仍然可用。默认值是：true。
      filename: 'chart',                    // 输出文件的文件名（不带后缀），默认是：chart。
      formAttributes: null,                 // 对象，用于对POST表单应用额外的属性，该表单负责向输出服务器发送SVG数据。默认是：null。
      scale: 2,                             // 定义了导出的图片相对于屏幕上图片大小的对比倍数或者放大倍数。默认是：2。
      sourceHeight: null,                   // 与sourceWidth类似
      sourceWidth: null,                    // 该项用于设置导出时原始图片的宽度，除非明确设置了chart.width。最后导出栅格图片的宽度等于原始图片的宽度乘以scale。
      type: 'image/png',                    // 如果chart.exportChart()被调用时，没有获得指定图片类型，该项作为默认输出的MIME类型。可选值包括image/png、image/jpeg、application/pdf和image/svg+xml。
      url: 'http://export.highcharts.com',  // 输出服务器的url。 默认是Highslide Software的免费网络服务地址。
      width: undefined,                     // 输出的PNG或JPG的宽度，单位px。Highcharts3.0及以上版本，默认的像素宽度是通过chart.width或者exporting.sourceWidth 和 exporting.scale来设置的。 默认值：undefined.
    }
```