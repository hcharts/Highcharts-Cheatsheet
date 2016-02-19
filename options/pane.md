# pane
#####只适用于极坐标图和角度测量仪
#####2016-02-19 @webkong
```
pane: {
      background: null,        // 一个对象或者一组对象作为背景。子选项中包含有backgroundColor (可以是实色也可以是渐变色)，shape (实体或圆弧)，innerWidth，outerWidth，borderWidth，borderColor。
      center: ['50%', '50%'],  // 极坐标或者角度仪表盘的中心，通过一个数组[x,y]来定位。位置可以通过整数或者百分比来设定，整数会被转换为像素；百分比是根据绘图区的大小来设定的。
      endAngle: null,          // 极坐标或者仪表盘的末端点角度，以度来计算，且北（方向）为0度。
      startAngle: null         // 极坐标或者仪表盘的始端点角度，以度来计算，且北（方向）为0度。
    },
```
