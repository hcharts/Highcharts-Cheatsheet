# Highcharts 参考手册。

这份文档是完整的 Highcharts API 及 词条的注释，我们要翻译的主要内容也就是 注释部分，所以分工也是按照API 的模块来。

## 一、翻译内容

1. HIGHCHARTS 全局配置   
2. HIGHCHARTS 主配置            
	* chart
	* colors
	* credits
	* drilldown
	* exporting
	* labels
	* legend
	* loading
	* navigation
	* noData
	* pane
	* plotOptions   （量非常大，也是 Highcharts 非常重要的配置）
	* series
	* subtitle
	* title
	* tooltip
	* xAxis
	* yAxis

3. HIGHCHARTS 方法和参数  

	* chart
	* axis
	* renderer
	* Highcharts
	* point
	* series



### 文档翻译内容及安排

<table>
	<tr>
		<th>章节</th>
		<th>翻译内容</th>
		<th>文件名</th>
		<th>负责人</th>
	</tr>

	<tr>
		<td rowspan=2>HIGHCHARTS 全局配置</td>
		<td>global</td>
		<td>global/global.md</td>
		<td>zhy1stgg</td>
	</tr>
	<tr>

		<td>lang</td>
		<td>global/global.md</td>
		<td>zhy1stgg</td>
	</tr>

	<tr>
		<td rowspan=16>HIGHCHARTS 主配置</td>
		<td>chart</td>
		<td>options/chart.md</td>
		<td></td>
	</tr>

	<tr>
		<td>colors</td>
		<td>options/colors.md</td>
		<td>cxytomo</td>
	</tr>

	<tr>
		<td>credits</td>
		<td>options/credits.md</td>
		<td>cxytomo</td>
	</tr>

	<tr>
		<td>drilldown</td>
		<td>options/drilldown.md</td>
		<td>cxytomo</td>
	</tr>

	<tr>
		<td>exporting</td>
		<td>options/exporting.md</td>
		<td>cxytomo</td>
	</tr>

	<tr>
		<td>labels</td>
		<td>options/labels.md</td>
		<td>zhuzisheng</td>
	</tr>

	<tr>
		<td>legend</td>
		<td>options/legend.md</td>
		<td>zhuzisheng</td>
	</tr>

	<tr>
		<td>loading</td>
		<td>options/loading.md</td>
		<td>zhuzisheng</td>
	</tr>


	<tr>
		<td>navigation</td>
		<td>options/navigation.md</td>
		<td>zhuzisheng</td>
	</tr>

	<tr>
		<td>noData</td>
		<td>options/nodata.md</td>
		<td>webkong</td>
	</tr>

	<tr>
		<td>pane</td>
		<td>options/pane.md</td>
		<td>webkong</td>
	</tr>

	<tr>
		<td>plotOptions</td>
		<td>options/plotOptions.md</td>
		<td></td>
	</tr>

	<tr>
		<td>series</td>
		<td>options/series.md</td>
		<td>webkong</td>
	</tr>

	<tr>
		<td>title & subtitle</td>
		<td>options/title.md</td>
		<td>webkong</td>
	</tr>

	<tr>
		<td>tooltip</td>
		<td>options/tooltip.md</td>
		<td></td>
	</tr>

	<tr>
		<td>xAxis & yAxis</td>
		<td>options/axis.md</td>
		<td></td>
	</tr>

	<tr>
		<td rowspan=7>HIGHCHARTS 方法</td>
		<td>Axis</td>
		<td>methods/Axis.md</td>
		<td>zhy1stgg</td>
	</tr>
	<tr>
		<td>Chart</td>
		<td>methods/Chart.md</td>
		<td>zhy1stgg</td>
	</tr>

	<tr>
		<td>Element</td>
		<td>methods/Element.md</td>
		<td>zhy1stgg</td>
	</tr>

	<tr>
		<td>Highcharts</td>
		<td>methods/Highcharts.md</td>
		<td>zhy1stgg</td>
	</tr>

	<tr>
		<td>Point</td>
		<td>methods/Point.md</td>
		<td>zhy1stgg</td>
	</tr>

	<tr>
		<td>Renderer</td>
		<td>methods/Renderer.md</td>
		<td>zhy1stgg</td>
	</tr>
	<tr>
		<td>Series</td>
		<td>methods/Series.md</td>
		<td>zhy1stgg</td>
	</tr>

</table>

## 相关说明

请参考  [http://www.hcharts.cn/api/index.php](http://www.hcharts.cn/api/index.php)  及 [highcharts-cheatsheet.md](highcharts-cheatsheet.md) ，在对应文件里写内容。

注意每个人只能修改自己负责的文件，不然会导致冲突，如果需要补充修改别人的内容，请提交 pull request.

###  创建 git 分支

建议每个人在自己的分支上操作，操作过程是：

```
git checkout -b "your branch name"
// 编辑
git add -A
git commit -m "commit message"
git checkout master
git merge "your branch name"
git status
git push origin master
```

git 教程请参考：http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000
