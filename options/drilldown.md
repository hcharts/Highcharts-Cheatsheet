# drilldown

###下钻图表选项

```js
drilldown: {
      activeAxisLabelStyle: null,  // 为可下钻点对应的x轴标签添加额外样式。默认效果是添加下划线，并显示蓝色文字。默认是：null。
      activeDataLabelStyle: null,  // 为可下钻点对应的数据标签添加额外样式。默认效果是添加下划线，并显示蓝色文字。默认是：null。
      animation: null,             // 设置所有下钻动作的动画效果。只有下钻前后的图形类型统一，才能呈现动画效果。默认是：null。
      drillUpButton: {             //设置下钻返回按钮
        position: null,            // 相对于“relativeTo”设置的区域进行定位。可使用配置项包括x、y、align和verticalAlign。默认是：null。
        relativeTo: 'plotBox',     // 设置用于定位的基准区域。可选值为“plotBox”或“spacingBox”。当值为plotBox，表示与绘图区对齐；当值为spacingBox，表示与图表区对齐。默认是：plotBox。
        theme: null                // 下钻返回按钮属性的集合。该对象可使用SVG属性，如fill、stroke、stroke-width 或圆角边框属性r(border radius)。默认是：null。
      },
      series: null                 // 该数组用来定义下钻数据列。 每个数据列的配置语法同series。默认是：null。
    }
```