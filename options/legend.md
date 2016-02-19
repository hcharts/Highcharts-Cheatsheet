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
}
```