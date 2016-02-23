# axis

###

```js
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
```
