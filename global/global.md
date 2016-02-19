# 全局配置

Highcharts 的全局配置是通过  ``` Highcharts.setOptions``` 进行配置，全局配置的属性对当前的所以图表有效，所以 Highcharts 默认提供全局属性 ``` global ``` 和 ``` lang ``` 都是通用的属性；另外，图表的主配置同样也可以写在 ``` setOptions```里。

```
// http://api.highcharts.com/highcharts#global

$(function() {

  // Highcharts.setOptions 里的配置对同一个页面的所有图表有效，也就是说对于多个图表公共的配置代码，完全可以放在 Highcharts.setOptions 里
  // 并且 $("#container").highcharts() 里的所有配置项对于 Highcharts.setOptions 都是可用的。

  Highcharts.setOptions({
    global: {                                    // 全局配置变量
      VMLRadialGradientURL: 'http://code.highcharts.com/{version}/gfx/vml-radial-gradient.png',  // Path to the pattern image required by VML browsers in order to draw radial gradients.
      canvasToolsURL: 'http://code.highcharts.com/{version}/modules/canvas-tools.js',            // The URL to the additional file to lazy load for Android 2.x devices. These devices don't support SVG, so we download a helper file that contains canvg, its dependecy rbcolor, and our own CanVG Renderer class.
      timezoneOffset: 0,  // 时区间隔，单位为 分钟。中国为 +8 区，如果图表中展示的时间和实际时间相差 8个小时，设置本参数为 -8 * 60 来调整
      useUTC: true        // Whether to use UTC time for axis scaling, tickmark placement and time display in Highcharts.dateFormat.
    },
    lang: {                                      // 图表中语言文字对象
      contextButtonTitle: 'Chart context menu',  // 用于导出模块，导出按钮的标题
      decimalPoint: '.',                         // Highcharts.numberFormat 函数默认的小数点符号
      downloadJPEG: 'Download JPEG image',       // 用于导出模块，下载 JPEG 图片显示的文字
      downloadPDF: 'Download PDF document',      // 用于导出模块，下载 PDF 文件显示的文字
      downloadSVG: 'Download SVG vector image',  // 用于导出模块，下载 SVG 文件显示的文字
      drillUpText: 'Back to {series.name}',      // 下钻后返回父级的文字
      loading: 'Loading...',                     // 在调用 chart.showLoading 后显示的加载中的文字
      months: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],  // An array containing the months names. Corresponds to the %B format in Highcharts.dateFormat().
      noData: 'No data to display',                      // The text to display when the chart contains no data. Requires the no-data module, see noData.
      numericSymbols: ['k', 'M', 'G', 'T', 'P', 'E'],    // Metric prefixes used to shorten high numbers in axis labels. Replacing any of the positions with null causes the full number to be written.
      printChart: 'Print chart',  // Exporting module only. The text for the menu item to print the chart.
      resetZoom: 'Reset zoom',    // The text for the label appearing when a chart is zoomed.
      resetZoomTitle: 'Reset zoom level 1:1',  // The tooltip title for the label appearing when a chart is zoomed.
      shortMonths: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],  // An array containing the months names in abbreviated form. Corresponds to the %b format in Highcharts.dateFormat().
      thousandsSep: ',',  // The default thousands separator used in the Highcharts.numberFormat method unless otherwise specified in the function arguments.
      weekdays: ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']  // An array containing the weekday names.
    }
  });
});
```
