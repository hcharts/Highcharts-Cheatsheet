
[Highcharts](http://www.highcharts.com/) is a complete charting library to create animated and dynamic charts with JavaScript. It works in all modern mobile and desktop browsers including the iPhone/iPad and Internet Explorer from version 6.

You can find below most of the available options so as to quickly browse every possibility.

*Highcharts currently supports line, spline, area, areaspline, column, bar, pie, scatter, angular gauges, arearange, areasplinerange, columnrange, bubble, box plot, error bars, funnel, waterfall and polar chart types.*

Note: [Read the official HighCharts API documentation.](Read the official HighCharts API documentation)

## 1. INSTALLATION.

Highcharts requires two files to run, highcharts.js and either jQuery, MooTools or Prototype or the Highcharts Standalone Framework which are used for some common JavaScript tasks.

```
<!-- http://www.highcharts.com/docs/getting-started/installation -->

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>
<script src="https://code.highcharts.com/highcharts.js"></script>
```

## 2. HIGHCHARTS GLOBAL OPTIONS.

```
// http://api.highcharts.com/highcharts#global

$(function() {
  // If you want to apply a set of options to all charts on the same page, use Highcharts.setOptions
  // You can find below only specific information to setOptions() but any option from $("#container").highcharts() works. (check 3.)
  Highcharts.setOptions({
    global: {
      VMLRadialGradientURL: 'http://code.highcharts.com/{version}/gfx/vml-radial-gradient.png',  // Path to the pattern image required by VML browsers in order to draw radial gradients.
      canvasToolsURL: 'http://code.highcharts.com/{version}/modules/canvas-tools.js',            // The URL to the additional file to lazy load for Android 2.x devices. These devices don't support SVG, so we download a helper file that contains canvg, its dependecy rbcolor, and our own CanVG Renderer class.
      timezoneOffset: 0,  // The timezone offset in minutes
      useUTC: true        // Whether to use UTC time for axis scaling, tickmark placement and time display in Highcharts.dateFormat.
    },
    lang: {
      contextButtonTitle: 'Chart context menu',  // Exporting module menu. The tooltip title for the context menu holding print and export menu items.
      decimalPoint: '.',                         // The default decimal point used in the Highcharts.numberFormat method unless otherwise specified in the function arguments.
      downloadJPEG: 'Download JPEG image',       // Exporting module only. The text for the JPEG download menu item.
      downloadPDF: 'Download PDF document',      // Exporting module only. The text for the PDF download menu item.
      downloadSVG: 'Download SVG vector image',  // Exporting module only. The text for the SVG download menu item.
      drillUpText: 'Back to {series.name}',      // The text for the button that appears when drilling down, linking back to the parent series.
      loading: 'Loading...',                     // The loading text that appears when the chart is set into the loading state following a call to chart.showLoading.
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

## 3. CREATE YOUR CHART.

```
<div id="container" style="width:100%; height:400px;"></div>
```

```
// http://api.highcharts.com/highcharts#chart

$(function () {
  $('#container').highcharts({
    chart: {
      alignTicks: true,           // When using multiple axis, the ticks of two or more opposite axes will automatically be aligned by adding ticks to the axis or axes with the least ticks.
      animation: true,            // Set the overall animation for all chart updating. Animation can be disabled throughout the chart by setting it to false here.
      backgroundColor: '#FFF',    // The background color or gradient for the outer chart area.
      borderColor: '#4572A7',     // The color of the outer chart border.
      borderRadius: 5,            // The corner radius of the outer chart border. In export, the radius defaults to 0. Defaults to 5.
      borderWidth: 0,             // The pixel width of the outer chart border.
      className: null,            // A CSS class name to apply to the charts container div, allowing unique CSS styling for each chart.
      defaultSeriesType: 'line',  // Alias of type.
      events: {
        addSeries: null,  // Fires when a series is added to the chart after load time, using the addSeries method. The this keyword refers to the chart object itself. One parameter, event, is passed to the function.
        click: null,      // Fires when clicking on the plot background. The this keyword refers to the chart object itself. One parameter, event, is passed to the function.
        drilldown: null,  // Fires when a drilldown point is clicked, before the new series is added. Event arguments include point for the originating point, and seriesOptions for the new series.
        drillup: null,    // Fires when drilling up from a drilldown series.
        load: null,       // Fires when the chart is finished loading. The this keyword refers to the chart object itself. One parameter, event, is passed to the function.
        redraw: null,     // Fires when the chart is redrawn, either after a call to chart.redraw() or after an axis, series or point is modified with the redraw option set to true. The this keyword refers to the chart object itself. One parameter, event, is passed to the function.
        selection: null   // Fires when an area of the chart has been selected. Selection is enabled by setting the chart's zoomType. The this keyword refers to the chart object itself. One parameter, event, is passed to the function.
      },
      height: null,              // An explicit height for the chart. By default the height is calculated from the offset height of the containing element, or 400 pixels if the containing element's height is 0.
      ignoreHiddenSeries: true,  // If true, the axes will scale to the remaining visible series once one series is hidden.
      inverted: false,           // Whether to invert the axes so that the x axis is vertical and y axis is horizontal. When true, the x axis is reversed by default. If a bar series is present in the chart, it will be inverted automatically.
      margin: [null],            // The margin between the outer edge of the chart and the plot area. The numbers in the array designate top, right, bottom and left respectively. Use the options marginTop, marginRight, marginBottom and marginLeft for shorthand setting of one option.
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
      type: 'line',                                // The default series type for the chart. Can be any of the chart types listed under plotOptions.
      width: null,                                 // An explicit width for the chart. By default the width is calculated from the offset width of the containing element.
      zoomType: null,                              // Decides in what dimentions the user can zoom by dragging the mouse. Can be one of x, y or xy.

    },
    colors: ['#7cb5ec', '#434348', '#90ed7d', '#f7a35c', '#8085e9', '#f15c80', '#e4d354', '#8085e8', '#8d4653', '#91e8e1'],  // An array containing the default colors for the chart's series. When all colors are used, new colors are pulled from the start again.
    credits: {
      enabled: true,                      // Whether to show the credits text.
      href: 'http://www.highcharts.com',  // The URL for the credits label.
      position: null,                     // Position configuration for the credtis label.
      style: null,                        // CSS styles for the credits label.
      text: 'Highcharts.com.'             // The text for the credits label.
    },
    drilldown: {
      activeAxisLabelStyle: null,  // Additional styles to apply to the X axis label for a point that has drilldown data.
      activeDataLabelStyle: null,  // Additional styles to apply to the data label of a point that has drilldown data.
      animation: null,             // Set the animation for all drilldown animations. Animation of a drilldown occurs when drilling between a column point and a column series, or a pie slice and a full pie series.
      drillUpButton: {
        position: null,            // Positioning options for the button within the relativeTo box. Available properties are x, y, align and verticalAlign.
        relativeTo: 'plotBox',     // What box to align the button to. Can be either "plotBox" or "spacingBox".
        theme: null                // A collection of attributes for the button. The object takes SVG attributes like fill, stroke, stroke-width or r, the border radius.
      },
      series: null                 // An array of series configurations for the drill down. Each series configuration uses the same syntax as the series option set.
    },
    exporting: {
      buttons: {
        contextButton: {
          align: 'right',         // Alignment for the buttons.
          enabled: true,          // Whether to enable buttons.
          height: 20,             // Pixel height of the buttons.
          menuItems: null,        // A collection of config options for the menu items. Each options object consists of a text option which is a string to show in the menu item, as well as an onclick parameter which is a callback function to run on click.
          onclick: null,          // A click handler callback to use on the button directly instead of the popup menu.
          symbol: 'menu',         // The symbol for the button. Points to a definition function in the Highcharts.Renderer.symbols collection. The default exportIcon function is part of the exporting module.
          symbolFill: '#A8BF77',  // See navigation.buttonOptions => symbolFill.
          symbolSize: 14,         // The pixel size of the symbol on the button.
          symbolStroke: 14,       // The color of the symbol's stroke or line.
          symbolStrokeWidth: 1,   // The pixel stroke width of the symbol on the button.
          symbolX: 12.5,          // The x position of the center of the symbol inside the button.
          symbolY: 10.5,          // The y position of the center of the symbol inside the button.
          text: null,             // A text string to add to the individual button.
          theme: null,            // A configuration object for the button theme. The object accepts SVG properties like stroke-width, stroke and fill.
          verticalAlign: 'top',   // The vertical alignment of the buttons. Can be one of "top", "middle" or "bottom".
          width: 24,              // The pixel width of the button.
          x: -10,                 // The horizontal positioin of the button relative to the align option.
          y: 0                    // The vertical offset of the button's position relative to its verticalAlign.
        }
      },
      chartOptions: null,                   // Additional chart options to be merged into an exported chart. For example, the exported chart can be given a specific width and height, or a printer-friendly color scheme.
      enabled: true,                        // Whether to enable the exporting module. Disabling the module will hide the context button, but API methods will still be available.
      filename: 'chart',                    // The filename, without extension, to use for the exported chart.
      formAttributes: null,                 // An object containing additional attributes for the POST form that sends the SVG to the export server.
      scale: 2,                             // Defines the scale or zoom factor for the exported image compared to the on-screen display.
      sourceHeight: null,                   // Analogous to sourceWidth
      sourceWidth: null,                    // The width of the original chart when exported, unless an explicit chart.width is set. The width exported raster image is then multiplied by scale.
      type: 'image/png',                    // Default MIME type for exporting if chart.exportChart() is called without specifying a type option. Possible values are image/png, image/jpeg, application/pdf and image/svg+xml.
      url: 'http://export.highcharts.com',  // The URL for the server module converting the SVG string to an image format. By default this points to Highslide Software's free web service.
      width: undefined,                     // The pixel width of charts exported to PNG or JPG. As of Highcharts 3.0, the default pixel width is a function of the chart.width or exporting.sourceWidth and the exporting.scale.
    },
    labels: {
      items: {
        html: null,  // Inner HTML or text for the label.
        style: null  // CSS styles for each label.
      },
      style: null    // Shared CSS styles for all labels.
    },
    legend: {
      align: 'center',           // The horizontal alignment of the legend box within the chart area. Valid values are "left", "center" and "right".
      backgroundColor: null,     // The background color of the legend, filling the rounded corner border.
      borderColor: '#909090',    // The color of the drawn border around the legend.
      borderRadius: 0,           // The border corner radius of the legend.
      borderWidth: 0,            // The width of the drawn border around the legend.
      enabled: true,             // Enable or disable the legend.
      floating: false,           // When the legend is floating, the plot area ignores it and is allowed to be placed below it.
      itemDistance: 20,          // In a legend with horizontal layout, the itemDistance defines the pixel distance between each item.
      itemHiddenStyle: null,     // CSS styles for each legend item when the corresponding series or point is hidden. Only a subset of CSS is supported, notably those options related to text. Properties are inherited from style unless overridden here.
      itemHoverStyle: null,      // CSS styles for each legend item in hover mode. Only a subset of CSS is supported, notably those options related to text. Properties are inherited from style unless overridden here.
      itemMarginBottom: 0,       // The pixel bottom margin for each legend item.
      itemMarginTop: 0,          // The pixel top margin for each legend item.
      itemStyle: { "color": "#333333", "cursor": "pointer", "fontSize": "12px", "fontWeight": "bold" },  // CSS styles for each legend item. Only a subset of CSS is supported, notably those options related to text.
      itemWidth: null,           // The width for each legend item. This is useful in a horizontal layout with many items when you want the items to align vertically.
      labelFormat: '{name}',     // A format string for each legend label. Available variables relates to properties on the series, or the point in case of pies.
      labelFormatter: null,      // Callback function to format each of the series' labels. The this keyword refers to the series object, or the point object in case of pie charts.
      layout: 'horizontal',      // The layout of the legend items. Can be one of "horizontal" or "vertical".
      lineHeight: 16,            // Line height for the legend items. Deprecated as of 2.1. Instead, the line height for each item can be set using itemStyle.lineHeight, and the padding between items using itemMarginTop and itemMarginBottom.
      margin: 15,                // If the plot area sized is calculated automatically and the legend is not floating, the legend margin is the space between the legend and the axis labels or plot area.
      maxHeight: null,           // Maximum pixel height for the legend. When the maximum height is extended, navigation will show.
      navigation: {
        activeColor: '#3E576F',  // The color for the active up or down arrow in the legend page navigation.
        animation: true,         // How to animate the pages when navigating up or down. A value of true applies the default navigation given in the chart.animation option. Additional options can be given as an object containing values for easing and duration.
        arrowSize: 12,           // The pixel size of the up and down arrows in the legend paging navigation.
        inactiveColor: '#CCC',   // The color of the inactive up or down arrow in the legend page navigation.
        style: null              // Text styles for the legend page navigation.
      },
      padding: 8,        // The inner padding of the legend box.
      reversed: false,   // Whether to reverse the order of the legend items compared to the order of the series or points as defined in the configuration object.
      rtl: false,        // Whether to show the symbol on the right side of the text rather than the left side. This is common in Arabic and Hebraic.
      shadow: false,     // Whether to apply a drop shadow to the legend. A backgroundColor also needs to be applied for this to take effect. Since 2.3 the shadow can be an object configuration containing color, offsetX, offsetY, opacity and width.
      symbolHeight: 12,  // The pixel height of the symbol for series types that use a rectangle in the legend.
      symbolPadding: 5,  // The pixel padding between the legend item symbol and the legend item text.
      symbolRadius: 2,   // The border radius of the symbol for series types that use a rectangle in the legend.
      symbolWidth: 16,   // The pixel width of the legend item symbol.
      title: {
        style: null,     // Generic CSS styles for the legend title.
        text: null       // A text or HTML string for the title.
      },
      useHTML: false,           // Whether to use HTML to render the legend item texts. When using HTML, legend.navigation is disabled.
      verticalAlign: 'bottom',  // The vertical alignment of the legend box. Can be one of "top", "middle" or "bottom". Vertical position can be further determined by the y option.
      width: null,              // The width of the legend box.
      x: 0,                     // The x offset of the legend relative to it's horizontal alignment align within chart.spacingLeft and chart.spacingRight. Negative x moves it to the left, positive x moves it to the right.
      y: 0                      // The vertical offset of the legend relative to it's vertical alignment verticalAlign within chart.spacingTop and chart.spacingBottom. Negative y moves it up, positive y moves it down.
    },
    loading: {
      hideDuration: 100,  // The duration in milliseconds of the fade out effect.
      labelStyle: null,   // CSS styles for the loading label span.
      showDuration: 100,  // The duration in milliseconds of the fade in effect.
      style: null         // CSS styles for the loading screen that covers the plot area.
    },
    navigation: {
      buttonOptions: {
        align: 'right',          // Alignment for the buttons.
        enabled: true,           // Whether to enable buttons.
        height: 20,              // Pixel height of the buttons.
        symbolFill: '#E0E0E0',   // Fill color for the symbol within the button.
        symbolSize: 14,          // The pixel size of the symbol on the button.
        symbolStroke: '#666',    // The color of the symbol's stroke or line.
        symbolStrokeWidth: 1,    // The pixel stroke width of the symbol on the button.
        symbolX: 12.5,           // The x position of the center of the symbol inside the button.
        symbolY: 10.5,           // The y position of the center of the symbol inside the button.
        text: null,              // A text string to add to the individual button.
        theme: null,             // A configuration object for the button theme. The object accepts SVG properties like stroke-width, stroke and fill. Tri-state button styles are supported by the states.hover and states.select objects.
        verticalAlign: 'top',    // The vertical alignment of the buttons. Can be one of "top", "middle" or "bottom".
        width: 24,               // The pixel width of the button.
        y: 0                     // The vertical offset of the button's position relative to its verticalAlign.
      },
      menuItemHoverStyle: null,  // CSS styles for the hover state of the individual items within the popup menu appearing by default when the export icon is clicked. The menu items are rendered in HTML.
      menuItemStyle: null,       // CSS styles for the individual items within the popup menu appearing by default when the export icon is clicked. The menu items are rendered in HTML.
      menuStyle: null            // CSS styles for the popup menu appearing by default when the export icon is clicked. This menu is rendered in HTML.
    },
    noData: {
      attr: null,                                                                  // An object of additional SVG attributes for the no-data label.
      position: { 'x': 0, 'y': 0, 'align': 'center', 'verticalAlign': 'middle' },  // The position of the no-data label, relative to the plot area.
      style: { "fontSize": "12px", "fontWeight": "bold", "color": "#60606a" }      // CSS styles for the no-data label.
    },
    pane: {
      background: null,        // An object, or array of objects, for backgrounds. Sub options include backgroundColor (can be solid or gradient), shape ("solid" or "arc"), innerWidth, outerWidth, borderWidth, borderColor.
      center: ['50%', '50%'],  // The center of a polar chart or angular gauge, given as an array of [x, y] positions. Positions can be given as integers that transform to pixels, or as percentages of the plot area size.
      endAngle: null,          // The end angle of the polar X axis or gauge value axis, given in degrees where 0 is north.
      startAngle: null         // The start angle of the polar X axis or gauge axis, given in degrees where 0 is north.
    },
    plotOptions: {
      // area, arearange, areaspline, areasplinerange, bar, boxplot, bubble, column, columnrange, errorbar, funnel, gauge, heatmap, line, pie, pyramid, scatter, series, solidgauge, spline, waterfall
      area: {
        allowPointSelect: false,  // Allow this series' points to be selected by clicking on the markers, bars or pie slices.
        animation: true,          // Enable or disable the initial animation when a series is displayed. The animation can also be set as a configuration object. Please note that this option only applies to the initial animation of the series itself. For other animations, see chart.animation and the animation parameter under the API methods.
        color: null,              // The main color or the series. In line type series it applies to the line and the point markers unless otherwise specified. In bar type series it applies to the bars unless a color is specified per point. The default value is pulled from the options.colors array.
        connectEnds: true,        // Polar charts only. Whether to connect the ends of a line series plot across the extremes.
        connectNulls: false,      // Whether to connect a graph line across null points.
        cropThreshold: 300,       // When the series contains less points than the crop threshold, all points are drawn, event if the points fall outside the visible plot area at the current zoom. The advantage of drawing all points (including markers and columns), is that animation is performed on updates.
        cursor: null,             // You can set the cursor to "pointer" if you have click events attached to the series, to signal to the user that the points and lines can be clicked.
        dashStyle: 'Solid',       // <A name for the dash style to use for the graph. Applies only to series type having a graph, like line, spline, area and scatter in case it has a lineWidth.
        dataLabels: {
          align: 'center',             // The alignment of the data label compared to the point. Can be one of "left", "center" or "right". Defaults to "center".
          backgroundColor: undefined,  // The background color or gradient for the data label.
          borderColor: undefined,      // The border color for the data label.
          borderRadius: 0,             // The border radius in pixels for the data label.
          borderWidth: 0,              // The border width in pixels for the data label.
          color: null,                 // The text color for the data labels.
          crop: true,                  // Whether to hide data labels that are outside the plot area. By default, the data label is moved inside the plot area according to the overflow option.
          defer: true,                 // Whether to defer displaying the data labels until the initial series animation has finished.
          enabled: false,              // Enable or disable the data labels.
          format: '{y}',               // A format string for the data label. Available variables are the same as for formatter.
          formatter: null,             // Callback JavaScript function to format the data label. Note that if a format is defined, the format takes precedence and the formatter is ignored.
          inside: null,                // For points with an extent, like columns, whether to align the data label inside the box or to the actual value point.
          overflow: 'justify',         // How to handle data labels that flow outside the plot area. The default is justify, which aligns them inside the plot area. For columns and bars, this means it will be moved inside the bar. To display data labels outside the plot area, set crop to false and overflow to "none".
          padding: 2,                  // When either the borderWidth or the backgroundColor is set, this     is the padding within the box.
          rotation: 0,                 // Text rotation in degrees. Note that due to a more complex structure, backgrounds and borders will be lost on a rotated data label.
          shadow: false,               // The shadow of the box. Works best with borderWidth or backgroundColor. Since 2.3 the shadow can be an object configuration containing color, offsetX, offsetY, opacity and width.
          style: null,                 // Styles for the label.
          useHTML: false,              // Whether to use HTML to render the labels.
          verticalAlign: null,         // The vertical alignment of a data label. Can be one of top, middle or bottom. The default value depends on the data, for instance in a column chart, the label is above positive values and below negative values.
          x: 0,                        // The x position offset of the label relative to the point.
          y: -6,                       // The y position offset of the label relative to the point.
          zIndex: 6                    // The Z index of the data labels. The default Z index puts it above the series. Use a Z index of 2 to display it behind the series.
        },
        enableMouseTracking: true,     // Enable or disable the mouse tracking for a specific series. This includes point tooltips and click events on graphs and points. For large datasets it improves performance.
        events: {
          afterAnimate: null,          // Fires after the series has finished its initial animation, or in case animation is disabled, immediately as the series is displayed.
          checkboxClick: null,         // Fires when the checkbox next to the series' name in the legend is clicked.. The this keyword refers to the series object itself. One parameter, event, is passed to the function. The state of the checkbox is found by event.checked. Return false to prevent the default action which is to toggle the select state of the series.
          click: null,                 // Fires when the series is clicked. The this keyword refers to the series object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts. Additionally, event.point holds a pointer to the nearest point on the graph.
          hide: null,                  // Fires when the series is hidden after chart generation time, either by clicking the legend item or by calling .hide().
          legendItemClick: null,       // Fires when the legend item belonging to the series is clicked. The this keyword refers to the series object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts. The default action is to toggle the visibility of the series. This can be prevented by returning false or calling event.preventDefault().
          mouseOut: null,              // Fires when the mouse leaves the graph. The this keyword refers to the series object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts. If the stickyTracking option is true, mouseOut doesn't happen before the mouse enters another graph or leaves the plot area.
          mouseOver: null,             // Fires when the mouse enters the graph. The this keyword refers to the series object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
          show: null,                  // Fires when the series is shown after chart generation time, either by clicking the legend item or by calling .show().
        },
        fillColor: null,               // Fill color or gradient for the area. When null, the series' color is used with the series' fillOpacity.
        fillOpacity: 0.75,             // Fill opacity for the area.
        lineColor: null,               // A separate color for the graph line. By default the line takes the color of the series, but the lineColor setting allows setting a separate color for the line without altering the fillColor.
        lineWidth: 2,                  // Pixel with of the graph line.
        linkedTo: null,                // The id of another series to link to. Additionally, the value can be ":previous" to link to the previous series. When two series are linked, only the first one appears in the legend. Toggling the visibility of this also toggles the linked series.
        marker: {
          enabled: true,               // Enable or disable the point marker.
          fillColor: null,             // The fill color of the point marker. When null, the series' or point's color is used.
          lineColor: '#FFFFFF',        // The color of the point marker's outline. When null, the series' or point's color is used.
          lineWidth: 0,                // The width of the point marker's outline.
          radius: 4,                   // The radius of the point marker.
          states: {
            hover: {
              enabled: true,           // Enable or disable the point marker.
              fillColor: null,         // The fill color of the marker in hover state.
              lineColor: '#FFFFFF',    // The color of the point marker's outline. When null, the series' or point's color is used.
              lineWidth: 0,            // The width of the point marker's outline.
              radius: null             // The radius of the point marker. In hover state, it defaults to the normal state's radius + 2.
            },
            select: {
              enabled: true,           // Enable or disable the point marker.
              fillColor: null,         // The fill color of the marker in hover state.
              lineColor: '#FFFFFF',    // The color of the point marker's outline. When null, the series' or point's color is used.
              lineWidth: 0,            // The width of the point marker's outline.
              radius: null             // The radius of the point marker. In hover state, it defaults to the normal state's radius + 2.
            }
          },
          symbol: null                 // A predefined shape or symbol for the marker. When null, the symbol is pulled from options.symbols. Other possible values are "circle", "square", "diamond", "triangle" and "triangle-down".
        },
        negativeColor: null,      // The color for the parts of the graph or points that are below the threshold.
        negativeFillColor: null,  // A separate color for the negative part of the area.
        point: {
          events: {
            click: null,      // Fires when a point is clicked. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
            mouseOut: null,   // Fires when the mouse leaves the area close to the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
            mouseOver: null,  // Fires when the mouse enters the area close to the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
            remove: null,     // Fires when the point is removed using the .remove() method. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
            select: null,     // Fires when the point is selected either programatically or following a click on the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
            unselect: null,   // Fires when the point is unselected either programatically or following a click on the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
            update: null      // Fires when the point is updated programmatically through the .update() method. The this keyword refers to the point object itself. One parameter, event, is passed to the function. The new point options can be accessed through event.options. Returning false cancels the operation.
          }
        },
        pointInterval: 1,      // If no x values are given for the points in a series, pointInterval defines the interval of the x values. For example, if a series contains one value every decade starting from year 0, set pointInterval to 10.
        pointPlacement: null,  // Possible values: null, "on", "between". In a column chart, when pointPlacement is "on", the point will not create any padding of the X axis. In a polar column chart this means that the first column points directly north. If the pointPlacement is "between", the columns will be laid out between ticks. This is useful for example for visualising an amount between two points in time or in a certain sector of a polar chart.
        pointStart: 0,         // If no x values are given for the points in a series, pointStart defines on what value to start. For example, if a series contains one yearly value starting from 1945, set pointStart to 1945. Defaults to 0.
        selected: false,       // Whether to select the series initially. If showCheckbox is true, the checkbox next to the series name will be checked for a selected series.
        shadow: false,         // Whether to apply a drop shadow to the graph line. Since 2.3 the shadow can be an object configuration containing color, offsetX, offsetY, opacity and width.
        showCheckbox: false,   // If true, a checkbox is displayed next to the legend item to allow selecting the series. The state of the checkbox is determined by the selected option.
        showInLegend: true,    // Whether to display this particular series or series type in the legend. The default value is true for standalone series, false for linked series.
        stacking: null,        // Whether to stack the values of each series on top of each other. Possible values are null to disable, "normal" to stack by value or "percent".
        states: {
          hover: {
            enabled: true,       // Enable separate styles for the hovered series to visualize that the user hovers either the series itself or the legend.
            halo: {
              attributes: null,  // A collection of SVG attributes to override the appearance of the halo, for example fill, stroke and stroke-width.
              opacity: 0.25,     // Opacity for the halo unless a specific fill is overridden using the attributes setting. Note that Highcharts is only able to apply opacity to colors of hex or rgb(a) formats.
              size: 10,          // The pixel size of the halo. For point markers this is the radius of the halo. For pie slices it is the width of the halo outside the slice. For bubbles it defaults to 5 and is the width of the halo outside the bubble.
            },
            lineWidth: 2,        // Pixel with of the graph line.
            marker: {
              enabled: true,         // Enable or disable the point marker.
              fillColor: null,       // The fill color of the point marker. When null, the series' or point's color is used.
              lineColor: '#FFFFFF',  // The color of the point marker's outline. When null, the series' or point's color is used.
              lineWidth: 0,          // The width of the point marker's outline.
              radius: 4,             // The radius of the point marker.
              symbol: null           // A predefined shape or symbol for the marker. When null, the symbol is pulled from options.symbols. Other possible values are "circle", "square", "diamond", "triangle" and "triangle-down".
            }
          }
        },
        stickyTracking: true,  // Sticky tracking of mouse events. When true, the mouseOut event on a series isn't triggered until the mouse moves over another series, or out of the plot area. When false, the mouseOut event on a series is triggered when the mouse leaves the area around the series' graph or markers.
        threshold: 0,          // The Y axis value to serve as the base for the area, for distinguishing between values above and below a threshold. If null, the area behaves like a line series with fill between the graph and the Y axis minimum.
        tooltip: {
          dateTimeLabelFormats: { millisecond:'%A, %b %e, %H:%M:%S.%L', second:'%A, %b %e, %H:%M:%S', minute:'%A, %b %e, %H:%M', hour:'%A, %b %e, %H:%M', day:'%A, %b %e, %Y', week:'Week from %A, %b %e, %Y', month:'%B %Y', year:'%Y' },  // For series on a datetime axes, the date format in the tooltip's header will by default be guessed based on the closest data points. This member gives the default string representations used for each unit. For an overview of the replacement codes, see dateFormat.
          followPointer: false,    // Whether the tooltip should follow the mouse as it moves across columns, pie slices and other point types with an extent. By default it behaves this way for scatter, bubble and pie series by override in the plotOptions for those series types.
          followTouchMove: false,  // Whether the tooltip should follow the finger as it moves on a touch device. The default value of false causes a touch move to scroll the web page, as is default behaviour on touch devices. Setting it to true may cause the user to be trapped inside the chart and unable to scroll away, so it should be used with care. If chart.zoomType is set, it will override followTouchMove.
          footerFormat: false,     // A string to append to the tooltip format.
          headerFormat: '<span style="font-size: 10px">{point.key}</span><br/>',  // The HTML of the tooltip header line. Variables are enclosed by curly brackets. Available variables     are point.key, series.name, series.color and other members from the point and series objects.
          hideDelay: 500,          // The number of milliseconds to wait until the tooltip is hidden when mouse out from a point or chart.
          pointFormat: '<span style="color:{series.color}">\u25CF</span> {series.name}: <b>{point.y}</b><br/>',  // The HTML of the point's line in the tooltip. Variables are enclosed by curly brackets. Available variables are point.x, point.y, series.name and series.color and other properties on the same form.
          shape: 'callout',        // The name of a symbol to use for the border around the tooltip. In Highcharts 3.x and less, the shape was square.
          valueDecimals: null,     // How many decimals to show in each series' y value. This is overridable in each series' tooltip options object.
          valuePrefix: null,       // A string to prepend to each series' y value. Overridable in each series' tooltip options object.
          valueSuffix: null,       // A string to append to each series' y value. Overridable in each series' tooltip options object.
          xDateFormat: null,       // The format for the date in the tooltip header if the X axis is a datetime axis. The default is a best guess based on the smallest distance between points in the chart.
        },
        trackByArea: false,        // Whether the whole area or just the line should respond to mouseover tooltips and other mouse or touch events.
        turboThreshold: 1000,      // When a series contains a data array that is longer than this, only one dimensional arrays of numbers, or two dimensional arrays with x and y values are allowed. Also, only the first point is tested, and the rest are assumed to be the same format. This saves expensive data checking and indexing in long series. Set it to 0 disable.
        visible: true              // Set the initial visibility of the series.
      }
    },
    series: {
      data: {
        color: null,        // Individual color for the point. By default the color is pulled from the global colors array.
        dataLabels: null,   // Individual data label for each point. The options are the same as the ones for plotOptions.series.dataLabels.
        drilldown: null,    // The id of a series in the drilldown.series array to use for a drilldown for this point.
        events: {
          click: null,      // Fires when a point is clicked. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
          mouseOut: null,   // Fires when the mouse leaves the area close to the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
          mouseOver: null,  // Fires when the mouse enters the area close to the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
          remove: null,     // Fires when the point is removed using the .remove() method. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
          select: null,     // Fires when the point is selected either programatically or following a click on the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
          unselect: null,   // Fires when the point is unselected either programatically or following a click on the point. The this keyword refers to the point object itself. One parameter, event, is passed to the function. Returning false cancels the operation.
          update: null      // Fires when the point is updated programmatically through the .update() method. The this keyword refers to the point object itself. One parameter, event, is passed to the function. The new point options can be accessed through event.options. Returning false cancels the operation.
        },
        id: null,                  // An id for the point. This can be used after render time to get a pointer to the point object through chart.get().
        isIntermediateSum: false,  // Waterfall series only. When this property is true, the points acts as a summary column for the values added or substracted since the last intermediate sum, or since the start of the series. The y value is ignored.
        isSum: false,              // Waterfall series only. When this property is true, the point display the total sum across the entire series. The y value is ignored.
        legendIndex: null,         // Pies only. The sequential index of the pie slice in the legend.
        marker: {
          enabled: true,         // Enable or disable the point marker.
          fillColor: null,       // The fill color of the point marker. When null, the series' or point's color is used.
          lineColor: '#FFFFFF',  // The color of the point marker's outline. When null, the series' or point's color is used.
          lineWidth: 0,          // The width of the point marker's outline.
          radius: 4,             // The radius of the point marker.
          states: {
            hover: {
              enabled: true,         // Enable or disable the point marker.
              fillColor: null,       // The fill color of the marker in hover state.
              lineColor: '#FFFFFF',  // The color of the point marker's outline. When null, the series' or point's color is used.
              lineWidth: 0,          // The width of the point marker's outline.
              radius: null           // The radius of the point marker. In hover state, it defaults to the normal state's radius + 2.
            },
            select: {
              enabled: true,         // Enable or disable the point marker.
              fillColor: null,       // The fill color of the marker in hover state.
              lineColor: '#FFFFFF',  // The color of the point marker's outline. When null, the series' or point's color is used.
              lineWidth: 0,          // The width of the point marker's outline.
              radius: null           // The radius of the point marker. In hover state, it defaults to the normal state's radius + 2.
            }
          },
          symbol: null    // A predefined shape or symbol for the marker. When null, the symbol is pulled from options.symbols. Other possible values are "circle", "square", "diamond", "triangle" and "triangle-down".
        },
        name: null,       // The name of the point as shown in the legend, tooltip, dataLabel etc.
        sliced: false,    // Pie series only. Whether to display a slice offset from the center.
        x: null,          // The x value of the point.
        y: null           // The y value of the point.
      },
      id: null,           // An id for the series. This can be used after render time to get a pointer to the series object through chart.get().
      index: null,        // The index of the series in the chart, affecting the internal index in the chart.series array, the visible Z index as well as the order in the legend.
      legendIndex: null,  // The sequential index of the series in the legend.
      name: null,         // The name of the series as shown in the legend, tooltip etc.
      stack: null,        // This option allows grouping series in a stacked chart. The stack option can be a string or a number or anything else, as long as the grouped series' stack options match each other.
      type: null,         // The type of series. Can be one of area, areaspline, bar, column, line, pie, scatter or spline. From version 2.3, arearange, areasplinerange and columnrange are supported with the highcharts-more.js component.
      xAxis: 0,           // When using dual or multiple x axes, this number defines which xAxis the particular series is connected to. It refers to either the axis id or the index of the axis in the xAxis array, with 0 being the first.
      yAxis: 0,           // When using dual or multiple y axes, this number defines which yAxis the particular series is connected to. It refers to either the axis id or the index of the axis in the yAxis array, with 0 being the first.
      zIndex: null,       // Define the visual z index of the series.
    },
    subtitle: {
      align: 'center',                // The horizontal alignment of the subtitle. Can be one of "left", "center" and "right".
      floating: false,                // When the subtitle is floating, the plot area will not move to make space for it.
      style: { 'color': '#555555' },  // CSS styles for the title. Exact positioning of the title can be achieved by changing the margin property, or by adding position: "absolute" and left and top properties.
      text: null,                     // The subtitle of the chart.
      useHTML: false,                 // Whether to use HTML to render the text.
      verticalAlign: null,            // The vertical alignment of the title. Can be one of "top", "middle" and "bottom". When a value is given, the title behaves as floating.
      x: 0,                           // The x position of the subtitle relative to the alignment within chart.spacingLeft and chart.spacingRight.
      y: null                         // The y position of the subtitle relative to the alignment within chart.spacingTop and chart.spacingBottom. By default the subtitle is laid out below the title unless the title is floating.
    },
    title: {
      align: 'center',                                    // The horizontal alignment of the title. Can be one of "left", "center" and "right".
      floating: false,                                    // When the title is floating, the plot area will not move to make space for it.
      margin: 15,                                         // The margin between the title and the plot area, or if a subtitle is present, the margin between the subtitle and the plot area.
      style: { 'color': '#333333', 'fontSize': '18px' },  // CSS styles for the title. Use this for font styling, but use align, x and yfor text alignment.
      text: 'Chart title',                                // The title of the chart. To disable the title, set the text to null.
      useHTML: false,                                     // Whether to use HTML to render the text.
      verticalAlign: null,                                // The vertical alignment of the title. Can be one of "top", "middle" and "bottom". When a value is given, the title behaves as floating.
      x: 0,                                               // The x position of the title relative to the alignment within chart.spacingLeft and chart.spacingRight.
      y: 15                                               // The y position of the title relative to the alignment within chart.spacingTop and chart.spacingBottom.
    },
    tooltip: {
      animation: true,                             // Enable or disable animation of the tooltip. In slow legacy IE browsers the animation is disabled by default.
      backgroundColor: rgba(255, 255, 255, 0.85),  // The background color or gradient for the tooltip.
      borderColor: 'auto',                         // The color of the tooltip border. When null, the border takes the color of the corresponding series or point.
      borderRadius: 3,                             // The radius of the rounded border corners.
      borderWidth: 1,                              // The pixel width of the tooltip border.
      crosshairs: null,                            // Display crosshairs to connect the points with their corresponding axis values. The crosshairs can be defined as a boolean, an array of booleans or an object.
      dateTimeLabelFormats: { millisecond:'%A, %b %e, %H:%M:%S.%L', second:'%A, %b %e, %H:%M:%S', minute:'%A, %b %e, %H:%M', hour:'%A, %b %e, %H:%M', day:'%A, %b %e, %Y', week:'Week from %A, %b %e, %Y', month:'%B %Y', year:'%Y' },  // For series on a datetime axes, the date format in the tooltip's header will by default be guessed based on the closest data points. This member gives the default string representations used for each unit. For an overview of the replacement codes, see dateFormat.
      enabled: true,           // Enable or disable the tooltip.
      followPointer: false,    // Whether the tooltip should follow the mouse as it moves across columns, pie slices and other point types with an extent. By default it behaves this way for scatter, bubble and pie series by override in the plotOptions for those series types.
      followTouchMove: false,  // Whether the tooltip should follow the finger as it moves on a touch device. The default value of false causes a touch move to scroll the web page, as is default behaviour on touch devices. Setting it to true may cause the user to be trapped inside the chart and unable to scroll away, so it should be used with care.
      footerFormat: false,     // A string to append to the tooltip format.
      formatter: null,         // Callback function to format the text of the tooltip. Return false to disable tooltip for a specific point on series.
      headerFormat: '<span style="font-size: 10px">{point.key}</span><br/>',  // The HTML of the tooltip header line. Variables are enclosed by curly brackets. Available variables     are point.key, series.name, series.color and other members from the point and series objects. The point.key variable contains the category name, x value or datetime string depending on the type of axis. For datetime axes, the point.key date format can be set using tooltip.xDateFormat.
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
    },
    // xAxis, yAxis
    xAxis: {
      allowDecimals: true,         // Whether to allow decimals in this axis' ticks. When counting integers, like persons or hits on a web page, decimals must be avoided in the axis tick labels.
      alternateGridColor: null,    // When using an alternate grid color, a band is painted across the plot area between every other grid line.
      categories: null,            // If categories are present for the xAxis, names are used instead of numbers for that axis. Since Highcharts 3.0, categories can also be extracted by giving each point a name and setting axis type to "category".
      ceiling: null,               // The highest allowed value for automatically computed axis extremes.
      dateTimeLabelFormats: { millisecond:'%A, %b %e, %H:%M:%S.%L', second:'%A, %b %e, %H:%M:%S', minute:'%A, %b %e, %H:%M', hour:'%A, %b %e, %H:%M', day:'%A, %b %e, %Y', week:'Week from %A, %b %e, %Y', month:'%B %Y', year:'%Y' },  // For series on a datetime axes, the date format in the tooltip's header will by default be guessed based on the closest data points. This member gives the default string representations used for each unit. For an overview of the replacement codes, see dateFormat.
      endOnTick: false,            // Whether to force the axis to end on a tick. Use this option with the maxPadding option to control the axis end.
      events: {
        afterSetExtremes: null,    // As opposed to the setExtremes event, this event fires after the final min and max values are computed and corrected for minRange.
        setExtremes: null          // Fires when the minimum and maximum is set for the axis, either by calling the .setExtremes() method or by selecting an area in the chart. The this keyword refers to the axis object itself. One parameter, event, is passed to the function. This contains common event information based on jQuery or MooTools depending on which library is used as the base for Highcharts.
      },
      floor: null,                 // The lowest allowed value for automatically computed axis extremes.
      gridLineColor: '#C0C0C0',    // Color of the grid lines extending the ticks across the plot area.
      gridLineDashStyle: 'solid',  // The dash or dot style of the grid lines. For possible values, see this demonstration.
      gridLineWidth: 0,            // The width of the grid lines extending the ticks across the plot area.
      gridZIndex: 1,               // The Z index of the grid lines.
      id: null,                    // An id for the axis. This can be used after render time to get a pointer to the axis object through chart.get().
      labels: {
        align: 'center',     // What part of the string the given position is anchored to. Can be one of "left", "center" or "right". Defaults to an intelligent guess based on which side of the chart the axis is on and the rotation of the label.
        distance: 15,        // Polar charts only. The label's pixel distance from the perimeter of the plot area.
        enabled: true,       // Enable or disable the axis labels.
        format: '{value}',   // A format string for the axis label.
        formatter: null,     // Callback JavaScript function to format the label. The value is given by this.value. Additional properties for this are axis, chart, isFirst and isLast.
        maxStaggerLines: 5,  // Horizontal axis only. When staggerLines is not set, maxStaggerLines defines how many lines the axis is allowed to add to automatically avoid overlapping X labels. Set to 1 to disable overlap detection.
        overflow: null,      // How to handle overflowing labels on horizontal axis. Can be undefined, false or "justify". By default it aligns inside the chart area. If "justify", labels will not render outside the plot area. If false, it will not be aligned at all. If there is room to move it, it will be aligned to the edge, else it will be removed.
        rotation: 0,         // Rotation of the labels in degrees.
        staggerLines: null,  // Horizontal axes only. The number of lines to spread the labels over to make room or tighter labels.
        step: null,          // To show only every n'th label on the axis, set the step to n. Setting the step to 2 shows every other label.
        style: null,         // CSS styles for the label. Use whiteSpace: 'nowrap' to prevent wrapping of category labels.
        useHTML: false,      // Whether to use HTML to render the labels.
        x: 0,                // The x position offset of the label relative to the tick position on the axis.
        y: 0,                // The y position offset of the label relative to the tick position on the axis.
        zIndex: 7,           // The Z index for the axis labels.
      },
      lineColor: '#C0D0E0',             // The color of the line marking the axis itself.
      lineWidth: 1,                     // The width of the line marking the axis itself.
      linkedTo: null,                   // Index of another axis that this axis is linked to. When an axis is linked to a master axis, it will take the same extremes as the master, but as assigned by min or max or by setExtremes. It can be used to show additional info, or to ease reading the chart by duplicating the scales.
      max: null,                        // The maximum value of the axis. If null, the max value is automatically calculated. If the endOnTick option is true, the max value might be rounded up. The actual maximum value is also influenced by chart.alignTicks.
      maxPadding: 0.01,                 // Padding of the max value relative to the length of the axis. A padding of 0.05 will make a 100px axis 5px longer. This is useful when you don't want the highest data value to appear on the edge of the plot area. When the axis' max option is set or a max extreme is set using axis.setExtremes(), the maxPadding will be ignored.
      min: null,                        // The minimum value of the axis. If null the min value is automatically calculated. If the startOnTick option is true, the min value might be rounded down.
      minPadding: 0.01,                 // Padding of the min value relative to the length of the axis. A padding of 0.05 will make a 100px axis 5px longer. This is useful when you don't want the lowest data value to appear on the edge of the plot area. When the axis' min option is set or a min extreme is set using axis.setExtremes(), the minPadding will be ignored.
      minRange: null,                   // The minimum range to display on this axis. The entire axis will not be allowed to span over a smaller interval than this. For example, for a datetime axis the main unit is milliseconds. If minRange is set to 3600000, you can't zoom in more than to one hour.
      minTickInterval: null,            // The minimum tick interval allowed in axis values. For example on zooming in on an axis with daily data, this can be used to prevent the axis from showing hours.
      minorGridLineColor: '#E0E0E0',    // Color of the minor, secondary grid lines.
      minorGridLineDashStyle: 'solid',  // The dash or dot style of the minor grid lines.
      minorGridLineWidth: 1,            // Width of the minor, secondary grid lines.
      minorTickColor: '#A0A0A0',        // Color for the minor tick marks.
      minorTickInterval: null,          // Tick interval in scale units for the minor ticks. On a linear axis, if "auto", the minor tick interval is calculated as a fifth of the tickInterval. If null, minor ticks are not shown.
      minorTickLength: 2,               // The pixel length of the minor tick marks.
      minorTickPosition: 'outside',     // The position of the minor tick marks relative to the axis line. Can be one of inside and outside.
      minorTickWidth: 0,                // The pixel width of the minor tick mark.
      offset: 0,                        // The distance in pixels from the plot area to the axis line. A positive offset moves the axis with it's line, labels and ticks away from the plot area. This is typically used when two or more axes are displayed on the same side of the plot.
      opposite: false,                  // Whether to display the axis on the opposite side of the normal. The normal is on the left side for vertical axes and bottom for horizontal, so the opposite sides will be right and top respectively. This is typically used with dual or multiple axes.
      plotBands: {
        color: null,   // The color of the plot band.
        events: null,  // An object defining mouse events for the plot band. Supported properties are click, mouseover, mouseout, mousemove.
        from: null,    // The start position of the plot band in axis units.
        id: null,      // An id used for identifying the plot band in Axis.removePlotBand.
        label: {
          align: 'center',       // Horizontal alignment of the label. Can be one of "left", "center" or "right".
          rotation: 0,           // Rotation of the text label in degrees.
          style: null,           // CSS styles for the text label.
          text: null,            // The string text itself. A subset of HTML is supported.
          textAlign: null,       // The text alignment for the label. While align determines where the texts anchor point is placed within the plot band, textAlign determines how the text is aligned against its anchor point. Possible values are "left", "center" and "right".
          useHTML: false,        // Whether to use HTML to render the labels.
          verticalAlign: 'top',  // Vertical alignment of the label relative to the plot band. Can be one of "top", "middle" or "bottom".
          x: null,               // Horizontal position relative the alignment.
          y: null,               // Vertical position of the text baseline relative to the alignment.
        },
        to: null,      // The end position of the plot band in axis units.
        zIndex: null,  // The z index of the plot band within the chart.
      },
      plotLines: {
        color: null,           // The color of the line.
        dashStyle: 'Solid',    // The dashing or dot style for the plot line.
        events: null,          // An object defining mouse events for the plot line. Supported properties are click, mouseover, mouseout, mousemove.
        id: null,              // An id used for identifying the plot line in Axis.removePlotLine.
        label: {
          align: 'left',       // Horizontal alignment of the label. Can be one of "left", "center" or "right".
          rotation: null,      // Rotation of the text label in degrees. Defaults to 0 for horizontal plot lines and 90 for vertical lines.
          style: null,         // CSS styles for the text label.
          text: null,          // The text itself. A subset of HTML is supported.
          textAlign: null,     // The text alignment for the label. While align determines where the texts anchor point is placed within the plot band, textAlign determines how the text is aligned against its anchor point. Possible values are "left", "center" and "right".
          useHTML: false,      // Whether to use HTML to render the labels.
          verticalAlign: top,  // Vertical alignment of the label relative to the plot band. Can be one of "top", "middle" or "bottom".
          x: null,             // Horizontal position relative the alignment.
          y: null              // Vertical position of the text baseline relative to the alignment.
        },
        value: null,  // The position of the line in axis units.
        width: null,  // The width or thickness of the plot line.
        zIndex: null  // The z index of the plot line within the chart.
      },
      reversed: false,               // Whether to reverse the axis so that the highest number is closest to the origin. If the chart is inverted, the x axis is reversed by default.
      showEmpty: true,               // Whether to show the axis line and title when the axis has no data.
      showFirstLabel: true,          // Whether to show the first tick label.
      showLastLabel: true,           // Whether to show the last tick label.
      startOfWeek: 1,                // For datetime axes, this decides where to put the tick between weeks. 0 = Sunday, 1 = Monday.
      startOnTick: false,            // Whether to force the axis to start on a tick. Use this option with the maxPadding option to control the axis start.
      tickColor: '#C0D0E0',          // Color for the main tick marks.
      tickInterval: null,            // The interval of the tick marks in axis units. When null, the tick interval is computed to approximately follow the tickPixelInterval on linear and datetime axes. On categorized axes, a null tickInterval will default to 1, one category. Note that datetime axes are based on milliseconds, so for example an interval of one day is expressed as 24 * 3600 * 1000.
      tickLength: 10,                // The pixel length of the main tick marks.
      tickPixelInterval: null,       // If tickInterval is null this option sets the approximate pixel interval of the tick marks. Not applicable to categorized axis. Defaults to 72 for the Y axis and 100 for    the X axis.
      tickPosition: 'outside',       // The position of the major tick marks relative to the axis line. Can be one of inside and outside.
      tickPositioner: null,          // A callback function returning array defining where the ticks are laid out on the axis. This overrides the default behaviour of tickPixelInterval and tickInterval.
      tickPositions: null,           // An array defining where the ticks are laid out on the axis. This overrides the default behaviour of tickPixelInterval and tickInterval.
      tickWidth: 1,                  // The pixel width of the major tick marks.
      tickmarkPlacement: 'between',  // For categorized axes only. If "on" the tick mark is placed in the center of the category, if "between" the tick mark is placed between categories.
      title: {
        align: 'middle',  // Alignment of the title relative to the axis values. Possible values are "low", "middle" or "high".
        margin: null,     // The pixel distance between the axis labels or line and the title. Defaults to 0 for horizontal axes, 10 for vertical.
        offset: null,     // The distance of the axis title from the axis line. By default, this distance is computed from the offset width of the labels, the labels' distance from the axis and the title's margin. However when the offset option is set, it overrides all this.
        rotation: 0,      // The rotation of the text in degrees. 0 is horizontal, 270 is vertical reading from bottom to top.
        style: { 'color': '#707070', 'fontWeight': 'bold' },  // CSS styles for the title. When titles are rotated they are rendered using vector graphic techniques and not all styles are applicable.
        text: null        // The actual text of the axis title. It can contain basic HTML text markup like <b>, <i> and spans with style.
      },
      type: 'linear'      // The type of axis. Can be one of "linear", "logarithmic", "datetime" or "category". In a datetime axis, the numbers are given in milliseconds, and tick marks are placed on appropriate values like full hours or days. In a category axis, the point names of the chart's series are used for categories, if not a categories array is defined.
    }
  });
});
```

## 4. METHODS AND PROPERTIES.

```
// http://api.highcharts.com/highcharts

var chart = new Highcharts.Chart(options);  // This is the constructor for creating a new chart object.
```

### 4.1. CHART.

```
// http://api.highcharts.com/highcharts#Chart

chart.container;  // A reference to the containing HTML element as given in chart.renderTo.
chart.options;    // The options stucture for the chart.
chart.series;     // An array of all the chart's series.
chart.xAxis;      // An array of the chart's x axes. If only one x axis, it is referenced by chart.xAxis[0].
chart.yAxis;      // An array of the chart's y axes. If only one y axis, it is referenced by chart.yAxis[0].

chart.addAxis(Object options, [Boolean isX], [Boolean redraw], [Mixed animation]){ };  // Add an axis to the chart after render time. Note that this method should never be used when adding data synchronously at chart render time, as it adds expense to the calculations and rendering. When adding data at the same time as the chart is initiated, add the axis as a configuration option instead.
chart.addSeries(Object options, [Boolean redraw], [Mixed animation]){ };               // Add a series to the chart after render time. Note that this method should never be used when adding data synchronously at chart render time, as it adds expense to the calculations and rendering. When adding data at the same time as the chart is initiated, add the series as a configuration option instead.
chart.addSeriesAsDrilldown(Object point, Object seriesOptions){ };                     // Add a series to the chart as drilldown from a specific point in the parent series. This method is used for async drilldown, when clicking a point in a series should result in loading and displaying a more high-resolution series. When not async, the setup is simpler using the drilldown.series options structure.
chart.destroy(){ };                                                                    // Removes the chart and purges memory. This method should be called beforewriting a new chart into the same container. It is called internally on window unloadto prevent leaks.
chart.drillUp(){ };                                                                    // When the chart is drilled down to a child series, calling chart.drillUp() will drill up to the parent series.
chart.exportChart(Object options, Object chartOptions){ };                             // Exporting module required. Submit an SVG version of the chart to a serveralong with some parameters for conversion.
chart.get(String id){ };                    // Get an axis, series or point by its id as given in the configuration options.
chart.getSVG(Object additionalOptions){ };  // Exporting module required. Get an SVG string representing the chart.
chart.getSelectedPoints(){ };               // Returns an array of all currently selected points in the chart. Points can be selected either programmatically by the point.select() method or by clicking.
chart.getSelectedSeries(){ };               // Returns an array of all currently selected series in the chart. Series can be selected either programmatically by the series.select() method or by checking the checkboxnext to the legend item if series.showCheckBox is true.
chart.hideLoading(){ };                     // Hide the loading screen. Options for the loadingscreen are defined at options.loading.
chart.print(){ };                           // Exporting module required. Clears away other elements in the page and printsthe chart as it is displayed. By default, when the exporting module is enabled,a button at the upper left calls this method.
chart.redraw(){ };                          // Redraw the chart after changes have been done to the data or axis extremes. All methods for updating axes, series or points have a parameter for redrawing the chart. This is true by default. But in many cases you want to do more than one operation on the chart before redrawing, for example add a number of points. In those cases it is a waste of resources to redraw the chart for each new point added. So you add the points and call chart.redraw() after.
chart.reflow(){ };                          // Reflows the chart to its container. By default, the chart reflows automatically to its container following a window.resize event, as per the chart.reflow option. However, there are no reliable events for div resize, so if the container is resized without a window resize event, this must be called explicitly.
chart.setSize(Number width, Number height, [Mixed animation]){ };  // Resize the chart to a given width and height.
chart.setTitle(Object title, object subtitle, Boolean redraw){ };  // Set a new title or subtitle for the chart
chart.showLoading(String str){ };
```

### 4.2. AXIS.

```
// http://api.highcharts.com/highcharts#Axis

chart.xAxis.addPlotBand(Object options){ };   // Add a plot band after render time.
chart.xAxis.addPlotLine (Object options){ };  // Add a plot line after render time.
chart.xAxis.getExtremes(){ };                 // Get the current extremes for the axis.
chart.xAxis.remove(Boolean redraw){ };        // Remove an axis from the chart.
chart.xAxis.removePlotBand(String id){ };     // Remove a plot band by its id.
chart.xAxis.removePlotLine(String id){ };     // Remove a plot line by its id.
chart.xAxis.setCategories(Array cateories, [Boolean redraw]){ };                          // Set new categories for the axis.
chart.xAxis.setExtremes(Number min, Number max, [Boolean redraw], [Mixed animation]){ };  // Set the minimum and maximum of the axes after render time. If the startOnTick and endOnTick options are true, the minimum and maximum values are rounded off to the nearest tick. To prevent this, these options can be set to false before calling setExtremes..
chart.xAxis.setTitle(Object title, [Boolean redraw]){ };                                  // Update the title of the axis after render time.
chart.xAxis.toPixels(Number value, [Boolean paneCoordinates]){ };                         // Translates a value in terms of axis units in to pixels within the chart.
chart.xAxis.toValue(Number pixel, [Boolean paneCoordinates]){ };                          // Translate a pixel position along the axis to a value in terms of axis units.
chart.xAxis.update(Object options, [Boolean redraw]){ };
```

### 4.3. ELEMENT.

```
// http://api.highcharts.com/highcharts#Element

chart.renderer.add([(Object parent)]){ };                          // Add the element to the renderer canvas.
chart.renderer.animate(Object attributes[, Object animation]){ };  // Apply numeric attributes to the SVG/VML element by animation. See Element.attr() for more information on setting attributes.
chart.renderer.attr(Object hash){ };                               // Apply attributes to the SVG/VML elements. These attributes for the most parts correspondto SVG, but some are specific to Highcharts, like zIndex and rotation.
chart.renderer.css(Object hash){ };                                // Apply some CSS properties to the element.
chart.renderer.destroy(){ };                                       // Destroy the element and free up memory.
chart.renderer.getBBox(){ };                                       // Get the bounding box of the element.
chart.renderer.on(String eventType, Function handler){ };          // Apply an event handler to the element.
chart.renderer.toFront(){ };                                       // Bring the element to the front. Alternatively, a zIndex attribute can be given.
```

### 4.4. HIGHCHARTS.

```
// http://api.highcharts.com/highcharts#Highcharts

Highcharts.charts;       // An array containing the current chart objects in the page. A chart's position in the array is preserved throughout the page's lifetime. When a chart is destroyed, the array item becomes undefined.
Highcharts.dateFormats;  // A hook for defining additional date format specifiers. New specifiers are defined as key-value pairs by using the specifier as key, and a function which takes the timestamp as value. This function returns the formatted portion of the date.

Highcharts.dateFormat(String format, [Number time], [Boolean capitalize]){ };  // Formats a JavaScript date timestamp (milliseconds since Jan 1st 1970) into a human readable date string. The format is a subset of the formats for PHP's strftime function. Additional formats can be given in the Highcharts.dateFormats hook, see below.
Highcharts.numberFormat(Number number, [Number decimals], [String decimalPoint], [String thousandsSep]){ };  // Formats a JavaScript number with grouped thousands, a fixed amount of decimals and an optional decimal point. It is a port of PHP's function with the same name. See PHP number_format for a full explanation of the parameters.
Highcharts.setOptions(Object options){ };  // Sets the options globally for all charts created after this has been called. Takes an options JavaScript object structure as the argument. These options are merged with the default options and the result is returned.
```

### 4.5. POINT.

```
// http://api.highcharts.com/highcharts#Point

chart.series[i].data[j].category;    // For categorized axes this property holds the category name for the point. For otheraxis it holds the x value.
chart.series[i].data[j].percentage;  // The percentage for points in a stacked series or pies.
chart.series[i].data[j].selected;    // Whether the point is selected or not.
chart.series[i].data[j].series;      // The series object associated with the point.
chart.series[i].data[j].x;           // The x value for the point.
chart.series[i].data[j].y;           // The y value for the point.

chart.series[i].data[j].remove([Boolean redraw], [Mixed animation]){ };     // Remove the point from the series.
chart.series[i].data[j].select([Boolean select], [Boolean accumulate]){ };  // Select or unselect the point.
chart.series[i].data[j].slice([Boolean sliced], [Boolean redraw], [Mixed animation]){ };  // Slice out or set back in a pie chart slice. This is the default wayof Highcharts to visualize that a pie point is selected..
chart.series[i].data[j].update([Mixed options], [Boolean redraw], [Mixed animation]){ };  // Update the point with new values.
```

### 4.7. SERIES.

```
// http://api.highcharts.com/highcharts#Series

chart.series[i].chart;     // Read only. The chart that the series belongs to.
chart.series[i].data;      // Read only. An array with the series' data point objects.
chart.series[i].name;      // The series' name as given in the options.
chart.series[i].options;   // Read only. The series' options.
chart.series[i].selected;  // Read only. The series' selected state as set by series.select().
chart.series[i].type;      // Read only. The series' type, like "line", "area" etc.
chart.series[i].visible;   // Read only. The series' visibility state as set by series.show(), series.hide(), or the initial configuration.
chart.series[i].xAxis;     // Read only. The unique yAxis object associated with the series.
chart.series[i].yAxis;     // Read only. The unique yAxis object associated with the series.

chart.series[i].addPoint(Object options, [Boolean redraw], [Boolean shift], [Mixed animation]){ };  // Add a point to the series after render time. The point can be added at the end, or by giving it an X value, to the start or in the middle of the series.
chart.series[i].hide(){ };  // Hides the series if visible. If the chart.ignoreHiddenSeries option is true,the chart is redrawn without this series.
chart.series[i].remove ([Boolean redraw]){ };  // Remove the series from the chart.
chart.series[i].select ([Boolean selected|null]){ };  //Select or unselect the series. This means its selected property is set,the checkbox in the legend is toggled and when selected, the series is returned in the chart.getSelectedSeries() method.
chart.series[i].setData (Array<Mixed> data, [Boolean redraw], [Mixed animation], [Boolean updatePoints]){ };  // Apply a new set of data to the series and optionally redraw it. Note that this method throws away all points and creates new ones. For updating the values of existing points, use Point.update() instead.
chart.series[i].setVisible (Boolean visible, [Boolean redraw]){ };  // A utility function to show or hide the series with an optional redraw.
chart.series[i].show (){ };  // Shows the series if hidden.
chart.series[i].update (Object options, [Boolean redraw]){ };  // Update the series with a new set of options. For a clean and precise handling of new options, all methods and elements from the series is removed, and it is initiated from scratch. Therefore, this method is more performance expensive than some other utility methods like setData or setVisible.
```
```



