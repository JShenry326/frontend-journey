# 1. 数据可视化前言



## 1.1 什么是数据可视化



数据可视化, 说白了, 就是把数据以更加直观的方式进行呈现. 那什么方式是更加直观的方式呢? 就是图表.
常言道, 文不如表, 表不如图, 人们大脑对图的敏感程度要比苍白无力的文字好很多.
我们来看一组数据.

```
衬衫:5
羊毛衫:20
雪纺衫:36
裤子:10
高跟鞋:10
袜子:20
```

这个数据就是某些产品的销量. 单纯从这些文字上来看, 很难看出数据之间对比的关系. 如果把这些数据以图表的方式呈现出来呢 ?



## 1.2 数据可视化的好处



- **清晰有效地传达与沟通信息**

数据可视化的好处之一就是能够清晰有效的传达信息和沟通信息. 继续看刚才的那个例子, 如果使
用同样的数据, 换成另外一种展现形式, 比如下边的这幅饼图. 我们可以很容易的就看出每个产品的
销量占比.不需要太多的脑力计算和思维转换

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818202037597.png" alt="image-20250818202037597" style="zoom:50%;" />

- **更容易洞察隐藏在数据中的信息**

将数据以图表的方式呈现出来还可以帮助我们感受到那些隐藏在数据之间的信息.比如下面的这幅上证指数的k线图

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818202125658.png" alt="image-20250818202125658" style="zoom:50%;" />

这幅图中可以看出指数的上升趋势或者下降趋势. 而上升趋势或者下降趋势这种信息是很难从文字中察觉到.



## 1.3 数据可视化的实现方式



- <font color='red'>报表类</font>
	- **Excel**
	- **水晶报表**

报表类的主要实现方式就大家熟悉的Excel或者水晶报表, 这种方式主要面向的是非技术人员, 在特定的软件中点击几个按钮,添加一些数据就可以生成图标了.这种方式的优点是简单, 谁都会用. 缺点也显而易见, 就是不灵活, 图表一旦生成之后就固定不变了, 如果数据发生变化了, 图表需要重新生成

- <font color='red'>商业智能 BI</font>
	- **Microsoft BI**
	- **Power-BI**

商业智能BI的实现方式主要有微软的BI和Power-BI, 它比报表类更加高端, 他除了可以对数据生成报表之外, 还可以提出决策依据，帮助企业做出明智的业务经营决策

- <font color='red'>编码类</font>

	- **ECharts.js**

	- **D3.js**

编码类, 这种是需要程序员参与, 程序员可以对接到公司现有的系统架构中进行编码, 实时生成动态的图表.常见的使用库有ECharts.js和D3.js, 我们项目中使用的是ECharts.js , 他是百度公司开发的一套开源可视化库, D3.js是国外的一个可视化库, 在封装性\易用性\效果上, ECharts要更优秀一些.

相对来说,这三种方式中编码类的实现方式更加灵活, 他可以融入到我们已有的项目中,和项目的贴合度是最高的, 但是他的门槛也高些, 需要有编程基础才能完成. 而我们的这么课程正是编码类可视化的实现, 并且选择的是百度开源的 ECharts.js .



# 2. ECharts的基本使用



## 2.1 ECharts的介绍



Charts是百度公司开源的一个使用 JavaScript 实现的开源可视化库，兼容性强，底层依赖矢量图形库 ZRender ，提供直观，交互丰富，可<font color='red'>高度个性化定制</font>的数据可视化图表。

- **开源免费**

它是开源免费的，也就是我们可以免费的使用 ECharts ，不需要缴纳任何的费用

- **功能丰富**

它的功能非常的丰富，提供了各种各样的图表，支持各种各样的定制, 满足各种需求，比如折线图、柱状图、饼图、K线图等. 在他的官方示例中, 提供了上百种图表, 可以用 只有你想不到, 没有她做不到 这句话来形容

- **社区活跃**

ECharts 的社区非常活跃，意味着你可以和很多开发者讨论，遇到了 ECharts 中不会的问题，也很容易找到解决办法

- **多种数据的支持**

可视化的含义就是将数据通过更加直观的图表的方式来呈现。图表只是一种呈现方式。最核心的其实是数据。 ECharts 对数据格式的支持也是非常友好的。 ECharts 能够支持常见的 key-value 数据格式，还能支持二维表，或者 TypedArray 格式的数据

- **流数据的支持**

对于超大的数据量而言， 数据本身的体量可能就非常消耗资源, 而 ECharts 可以支持对流数据的动态渲染，加载多少数据就渲染多少数据，省去了漫长的数据加载的等待时间, 他还提供了增量渲染的技术, 只渲染变化的数据, 提高系统的资源利用.

- **移动端的优化**

- **跨平台**
- **酷炫的特效**
- **数据的三维可视化**

- …

ECharts 能够做出各种各样漂亮的图表，它能满足绝大多数可视化图表的实现.它的兼容性强, 使用方便,功能强大, 是实现数据可视化的最佳选择之一, 更多特点和介绍可以查阅官网地址：https://echarts.apache.org/zh/index.html



## 2.2 ECharts的快速上手



ECharts 的入门使用特别简单, 5分钟就能够上手. 他大体分为这几个步骤

- **步骤1：引入 echarts.js 文件**

echarts是一个 js 的库，当然得先引入这个库文件

```html
<script src="js/echarts.min.js"></script>
```

- **步骤2：准备一个呈现图表的盒子**

这个盒子通常来说就是我们熟悉的 div ，这个 div 决定了图表显示在哪里

```html
<div id="main" style="width: 600px;height:400px;"></div>
```

- **步骤3：初始化 echarts 实例对象**

在这个步骤中, 需要指明图表最终显示在哪里的DOM元素

```javascript
var myChart = echarts.init(document.getElementById('main'))
```

- **步骤4：准备配置项**

这步很关键，我们最终的效果，到底是显示饼图还是折线图，基本上都是由配置项决定的

```javascript
var option = {
	xAxis: {
		type: 'category',
		data: ['小明', '小红', '小王']
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			name: '语文',
			type: 'bar',
			data: [70, 92, 87],
		}
	]
}
```

- **步骤5：将配置项设置给 echarts 实例对象**

```javascript
myChart.setOption(option)
```

通过简单的5个步骤, 就能够把一个简单的柱状图给显示在网页中了.这几个步骤中, 步骤4最重要,

一个图表最终呈现什么样子,完全取决于这个配置项.所以对于不同的图表, <font color='red'>除了配置项会发生改变</font>之外,其他的代码 都是<font color='red'>固定不变</font>的



## 2.3 相关配置讲解



- xAxis

	直角坐标系 中的 x 轴, 如果 type 属性的值为 category ,那么需要配置 data 数据, 代表在 x 轴的呈现

- yAxis

	直角坐标系 中的 y 轴, 如果 type 属性配置为 value , 那么无需配置 data , 此时 y 轴会自动去series 下找数据进行图表的绘制

	series

- 系列列表。每个系列通过 type 决定自己的图表类型, data 来设置每个系列的数据

配置项都是以键值对的形式存在, 并且配置项有很多, ECharts 的学习大多是针对于这些配置项的, 对于配置项的学习, 大家可以不用死记硬背, 需要的时候查一查官方文档即可. 网址:https://echarts.apache.org/zh/option.html , 常用的配置项多用几次, 你自然而然就记下了



# 3. ECharts常用图表



## 3.1 图表1 柱状图



### 3.1.1 柱状图的实现步骤



- **步骤1 ECharts 最基本的代码结构**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<script src="js/echarts.min.js"></script>
</head>
<body>
	<div style="width: 600px;height:400px"></div>
	<script>
		var mCharts = echarts.init(document.querySelector("div"))
		var option = {}
		mCharts.setOption(option)
	</script>
</body>
</html>
```

此时 option 是一个空空如也的对象

- **步骤2 准备x轴的数据**

```javascript
var xDataArr = ['张三', '李四', '王五', '闰土', '小明', '茅台', '二妞', '大强']
```

- **步骤3 准备 y 轴的数据**

```javascript
var yDataArr = [88, 92, 63, 77, 94, 80, 72, 86]
```

- **步骤4 准备 option , 将 series 中的 type 的值设置为: bar**

```javascript
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			type: 'bar',
			data: yDataArr
		}
	]
}
```

<font color='red'>注意: </font>坐标轴 xAxis 或者 yAxis 中的配置, type 的值主要有两种: category 和 value , 如果 type属性的值为 category ,那么需要配置 data 数据, 代表在 x 轴的呈现. 如果 type 属性配置为 value ,那么无需配置 data , 此时 y 轴会自动去 series 下找数据进行图表的绘制

最终的效果如下图:

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818203710306.png" alt="image-20250818203710306" style="zoom:50%;" />



### 3.1.2 柱状图的常见效果



<font color='red'>标记:</font>

- **最大值\最小值 markPoint**

```javascript
series: [
	{
		......
		markPoint: {
			data: [
				{
					type: 'max', name: '最大值'
				},
				{
					type: 'min', name: '最小值'
				}
			]
		}
	}
]
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818203833812.png" alt="image-20250818203833812" style="zoom:50%;" />

- **平均值 markLine**

```javascript
series: [
	{
		......
		markLine: {
			data: [
				{
					type: 'average', name: '平均值'
				}
			]
		}
	}
]
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204004400.png" alt="image-20250818204004400" style="zoom:50%;" />

<font color='red'>显示</font>

- **数值显示 label**

```java
series: [
	{
		......
		label: {
			show: true, // 是否可见
			rotate: 60 // 旋转角度
		}
	}
]
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204056565.png" alt="image-20250818204056565" style="zoom:50%;" />

- **柱宽度 barWidth**

```javascript
series: [
	{
		......
		barWidth: '30%' // 柱的宽度
	}
]
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204138467.png" alt="image-20250818204138467" style="zoom:50%;" />

- **横向柱状图**

所谓的横向柱状图, 只需要让x轴的角色和y轴的角色互换一下即可. 既 xAxis 的 type 设置为value , yAxis 的 type 设置为 category , 并且设置 data 即可

```javascript
var option = {
	xAxis: {
		type: 'value'
	},
	yAxis: {
		type: 'category',
		data: xDataArr
	},
	series: [
		{
			type: 'bar',
			data: yDataArr
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204239234.png" alt="image-20250818204239234" style="zoom:50%;" />



### 3.1.3 柱状图特点



柱状图描述的是分类数据，呈现的是每一个分类中<font color='red'>『有多少？』</font>, 图表所表达出来的含义在于不同类别数据的排名\对比情况



### 3.1.4 通用配置



使用 ECharts 绘制出来的图表, 都天生就自带一些功能, 这些功能是每一个图表都具备的, 我们可以通过配置, 对这些功能进行设置.

- **标题: title**

```javascript
var option = {
	title: {
		text: "成绩", // 标题文字
		textStyle: {
			color: 'red' // 文字颜色
		},
		borderWidth: 5, // 标题边框
		borderColor: 'green', // 标题边框颜色
		borderRadius: 5, // 标题边框圆角
		left: 20, // 标题的位置
		top: 20 // 标题的位置
	}
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204414517.png" alt="image-20250818204414517" style="zoom:50%;" />

- **提示框: tooltip**

tooltip 指的是当鼠标移入到图表或者点击图表时, 展示出的提示框

​	①触发类型: trigger

```
可选值有item\axis
```

​	②触发时机: triggerOn

```
可选值有 mouseOver\click
```

​	③格式化显示: formatter

​		⑴字符串模板

```javascript
var option = {
	tooltip: {
		trigger: 'item',
		triggerOn: 'click',
		formatter: '{b}:{c}'
	}
}
这个{b} 和 {c} 所代表的含义不需要去记, 在官方文档中有详细的描述
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204700484.png" alt="image-20250818204700484"  />

​		⑵回调函数

```javascript
var option = {
	tooltip: {
		trigger: 'item',
		triggerOn: 'click',
		formatter: function (arg) {
			return arg.name + ':' + arg.data
		}
	}
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204751877.png" alt="image-20250818204751877" style="zoom:50%;" />

- **工具按钮: toolbox**

toolbox 是 ECharts 提供的工具栏, 内置有 导出图片，数据视图, 重置, 数据区域缩放, 动态类型切换五个工具
工具栏的按钮是配置在 feature 的节点之下

```javascript
var option = {
	toolbox: {
		feature: {
			saveAsImage: {}, // 将图表保存为图片
			dataView: {}, // 是否显示出原始数据
			restore: {}, // 还原图表
			dataZoom: {}, // 数据缩放
			magicType: { // 将图表在不同类型之间切换,图表的转换需要数据的支持
				type: ['bar', 'line']
			}
		}
	}
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818204915356.png" alt="image-20250818204915356" style="zoom:50%;" />

- **图例: legend**

legend 是图例,用于筛选类别,需要和 series 配合使用

- legend 中的 data 是一个数组
- legend 中的 data 的值需要和 series 数组中某组数据的 name 值一致

```javascript
var option = {
	legend: {
		data: ['语文', '数学']
	},
	xAxis: {
		type: 'category',
		data: ['张三', '李四', '王五', '闰土', '小明', '茅台', '二妞', '大强']
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			name: '语文',
			type: 'bar',
			data: [88, 92, 63, 77, 94, 80, 72, 86]
		}, {
			name: '数学',
			type: 'bar',
			data: [93, 60, 61, 82, 95, 70, 71, 86]
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818210150600.png" alt="image-20250818210150600" style="zoom:50%;" />



## 3.2 图表2 折线图



### 3.2.1 折线图的实现步骤



- **步骤1 ECharts 最基本的代码结构**

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
	<script src="js/echarts.min.js"></script>
</head>
<body>
	<div style="width: 600px;height:400px"></div>
	<script>
		var mCharts = echarts.init(document.querySelector("div"))
		var option = {}
		mCharts.setOption(option)
	</script>
</body>
</html>
```

此时 option 是一个空空如也的对象

- **步骤2 准备 x 轴的数据**

```javascript
var xDataArr = ['1月', '2月', '3月', '4月', '5月', '6月', '7月', '8月', '9月','10月', '11月', '12月']
```

- **步骤3 准备 y 轴的数据**

```javascript
var yDataArr = [3000, 2800, 900, 1000, 800, 700, 1400, 1300, 900, 1000, 800, 600]
```

- **步骤4 准备 option , 将 series 中的 type 的值设置为: line**

```javascript
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			type: 'line',
			data: yDataArr
		}
	]
}
```

最终的效果如下:

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818212621933.png" alt="image-20250818212621933" style="zoom:50%;" />



### 3.2.2 折线图的常见效果



<font color='red'>标记</font>

- **最大值\最小值 markPoint**

```javascript
var option = {
	series: [
		{
			......
			markPoint: {
				data: [
					{
						type: 'max',
						name: '最大值'
					}, {
						type: 'min',
						name: '最小值'
					}
				]
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818212824497.png" alt="image-20250818212824497" style="zoom:50%;" />

- **平均值 markLine**

```javascript
var option = {
	series: [
		{
			......
			markLine: {
				data: [
					{
						type: 'average',
						name: '平均值'
					}
				]
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818212942473.png" alt="image-20250818212942473" style="zoom:50%;" />

- **标注区间 markArea**

```javascript
var option = {
	series: [
		{
			......
			markArea: {
				data: [
					[
						{
							xAxis: '1月'
						}, {
							xAxis: '2月'
						}
					],
					[
						{
							xAxis: '7月'
						}, {
							xAxis: '8月'
						}
					]
				]
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213156798.png" alt="image-20250818213156798" style="zoom:50%;" />

<font color='red'>线条控制</font>

- **平滑线条 smooth**

```javascript
var option = {
	series: [
		{
			......
			smooth: true
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213300315.png" alt="image-20250818213300315" style="zoom:50%;" />

- **线条样式 lineStyle**

```javascript
var option = {
	series: [
		{
			......
			smooth: true,
			lineStyle: {
				color: 'green',
				type: 'dashed' // 可选值还有 dotted solid
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213345152.png" alt="image-20250818213345152" style="zoom:50%;" />

<font color='red'>填充风格 areaStyle</font>

```javascript
var option = {
	series: [
		{
			type: 'line',
			data: yDataArr,
			areaStyle: {
				color: 'pink'
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213433589.png" alt="image-20250818213433589" style="zoom:50%;" />

<font color='red'>紧挨边缘 boundaryGap</font>

boundaryGap 是设置给 x 轴的, 让起点从 x 轴的0坐标开始

```javascript
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr,
		boundaryGap: false
	}
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213553628.png" alt="image-20250818213553628" style="zoom:50%;" />

<font color='red'>缩放, 脱离0值比例</font>

- 如果每一组数据之间相差较少, 且都比0大很多, 那么有可能会出现这种情况

```javascript
var yDataArr = [3005, 3003, 3001, 3002, 3009, 3007, 3003, 3001, 3005,3004, 3001, 3009] // 此时y轴的数据都在3000附近, 每个数之间相差不多
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			type: 'line',
			data: yDataArr
		}
	]
}
```

效果如下图:

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213701576.png" alt="image-20250818213701576" style="zoom:50%;" />

这显然不是我们想要的效果, 因此可以配置上 scale , 让其摆脱0值比例

- scale 配置

	scale 应该配置给 y 轴

```javascript
var option = {
	yAxis: {
		type: 'value',
		scale: true
	}
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818213751310.png" alt="image-20250818213751310" style="zoom:50%;" />

<font color='red'>堆叠图</font>

堆叠图指的是, 同个类目轴上系列配置相同的 stack 值后，后一个系列的值会在前一个系列的值上相加
如果在一个图表中有两个或者多个折线图, 在没有使用堆叠配置的时候, 效果如下:

```javascript
<script>
	var mCharts = echarts.init(document.querySelector("div"))
	var xDataArr = ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
	var yDataArr1 = [120, 132, 101, 134, 90, 230, 210]
	var yDataArr2 = [20, 82, 191, 94, 290, 330, 310]
	var option = {
		xAxis: {
			type: 'category',
			data: xDataArr
		},
		yAxis: {
			type: 'value',
			scale: true
		},
		series: [
			{
				type: 'line',
				data: yDataArr1
			},
			{
				type: 'line',
				data: yDataArr2
			}
		]
	}
	mCharts.setOption(option)
</script>
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818214319739.png" alt="image-20250818214319739" style="zoom:50%;" />

使用了堆叠图之后:

```javascript
var option = {
	series: [
		{
			type: 'line',
			data: yDataArr1,
			stack: 'all' // series中的每一个对象配置相同的stack值, 这个all可以任意写
		},
		{
			type: 'line',
			data: yDataArr2,
			stack: 'all' // series中的每一个对象配置相同的stack值, 这个all可以任意写
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818214412526.png" alt="image-20250818214412526" style="zoom:50%;" />

蓝色这条线的y轴起点, 不再是y轴, 而是红色这条线对应的点. 所以相当于蓝色是在红色这条线的基础之上进行绘制. 基于前一个图表进行堆叠



### 3.2.3 折线图的特点



折线图更多的使用来呈现数据随时间的<font color='red'>『变化趋势』</font>



## 3.3 图表3 散点图



### 3.3.1.散点图的实现步骤



- **步骤1 ECharts 最基本的代码结构**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<script src="js/echarts.min.js"></script>
</head>
<body>
	<div style="width: 600px;height:400px"></div>
	<script>
		var mCharts = echarts.init(document.querySelector("div"))
		var option = {}
		mCharts.setOption(option)
	</script>
</body>
</html>
```

此时 option 是一个空空如也的对象

- **步骤2 准备 x 轴和 y 轴的数据**

```javascript
var data = [{ "gender": "female", "height": 161.2, "weight": 51.6 }, {
"gender": "female", "height": 167.5, "weight": 59 }, { "gender": "female",
"height": 159.5, "weight": 49.2 }, { "gender": "female", "height": 157,
"weight": 63 }, { "gender": "female", "height": 155.8, "weight": 53.6 }, {
"gender": "female", "height": 170, "weight": 59 }, { "gender": "female",
"height": 159.1, "weight": 47.6 }, { "gender": "female", "height": 166,
"weight": 69.8 }, { "gender": "female", "height": 176.2, "weight": 66.8 }, {
"gender": "female", "height": 160.2, "weight": 75.2 }, { "gender": "female",
"height": 172.5, "weight": 55.2 }, { "gender": "female", "height": 170.9,
"weight": 54.2 }, { "gender": "female", "height": 172.9, "weight": 62.5 }, {
"gender": "female", "height": 153.4, "weight": 42 }, { "gender": "female",
"height": 160, "weight": 50 }, { "gender": "female", "height": 147.2,
"weight": 49.8 },...此处省略...]
```

假设这个数据是从服务器获取到的, 数组中的每一个元素都包含3个维度的数据: 性别,身高,体重, 而散点图需要的数据是一个二维数组, 所以我们需要将从服务器获取到的这部分数据,通过代码生成散点图需要的数据

```js
var axisData = []
for (var i = 0; i < data.length; i++) {
	var height = data[i].height
	var weight = data[i].weight
	var itemArr = [height, weight]
	axisData.push(itemArr)
}
```

axisData 就是一个二维数组, 数组中的每一个元素还是一个数组, 最内层数组中有两个元素, 一个代表身高, 一个代表体重

- **步骤3 准备配置项**

	- Axis 和 yAxis 的 type 都要设置为 value

	- 在 series 下设置 type:scatter

```js
var option = {
	xAxis: {
		type: 'value'
	},
	yAxis: {
		type: 'value'
	},
	series: [
		{
			type: 'scatter',
			data: axisData
		}
	]
}
```

- **步骤4 调整配置项, 脱离0值比例**
	- 给 xAxis 和 yAxis 配置 scale 的值为 true

```js
var option = {
	xAxis: {
		type: 'value',
		scale: true
	},
	yAxis: {
		type: 'value',
		scale: true
	},
	series: [
		{
			type: 'scatter',
			data: axisData,
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818214937256.png" alt="image-20250818214937256" style="zoom:50%;" />

### 3.3.2.散点图的常见效果



- **气泡图效果**

要能够达到气泡图的效果, 其实就是让每一个散点的大小不同, 让每一个散点的颜色不同

- symbolSize 控制散点的大小
- itemStyle.color 控制散点的颜色

这两个配置项都支持固定值的写法, 也支持回调函数的写法

固定值的写法如下:

```js
var option = {
	series: [
		{
			type: 'scatter',
			data: axisData,
			symbolSize: 25,
			itemStyle: {
				color: 'green',
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818215052059.png" alt="image-20250818215052059" style="zoom:50%;" />

回调函数的写法如下:

```js
var option = {
	series: [
		{
			type: 'scatter',
			data: axisData,
			symbolSize: function (arg) {
				var weight = arg[1]
				var height = arg[0] / 100
				// BMI > 28 则代表肥胖, 肥胖的人用大的散点标识, 正常的人用小散点标识
				// BMI: 体重/ 身高*身高 kg m
				var bmi = weight / (height * height)
				if (bmi > 28) {
					return 20
				}
				return 5
			},
			itemStyle: {
				color: function (arg) {
					var weight = arg.data[1]
					var height = arg.data[0] / 100
					var bmi = weight / (height * height)
					if (bmi > 28) {
						return 'red'
					}
					return 'green'
				}
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818215218836.png" alt="image-20250818215218836" style="zoom:50%;" />

- **涟漪动画效果**

​	①type:effectScatter

​		将 type 的值从 scatter 设置为 effectScatter 就能够产生涟漪动画的效果

​	②rippleEffect

​		rippleEffect 可以配置涟漪动画的大小

```js
var option = {
	series: [
		{
			type: 'effectScatter',
			rippleEffect:{
				scale:3
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818215422419.png" alt="image-20250818215422419" style="zoom:50%;" />

​	③showEffectOn

​		showEffectOn 可以控制涟漪动画在什么时候产生, 它的可选值有两个: render 和 emphasis
​		render 代表界面渲染完成就开始涟漪动画
​		emphasis 代表鼠标移过某个散点的时候, 该散点开始涟漪动画

```js
var option = {
	series: [
		{
			type: 'effectScatter',
			showEffectOn: 'emphasis',
			rippleEffect:{
				scale:3
			}
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818215537620.png" alt="image-20250818215537620" style="zoom:50%;" />

- **结合地图**

散点图也经常结合地图来进行地图区域的标注, 这个效果将在讲解地图时实现



### 3.3.3.散点图的特点



散点图可以帮助我们推断出<font color='red'>不同维度数据之间的相关性</font>, 比如上述例子中,看得出身高和体重是正相关, 身高越高, 体重越重

散点图也经常用在<font color='red'>地图的标注</font>上



### 3.3.4.直角坐标系的常见配置



直角坐标系的图表指的是带有x轴和y轴的图表, 常见的直角坐标系的图表有: 柱状图 折线图 散点图

针对于直角坐标系的图表, 有一些通用的配置

<font color='red'>配置1: 网格 grid</font>

grid是用来控制直角坐标系的布局和大小, x轴和y轴就是在grid的基础上进行绘制的

- **显示 grid**

	- show: true

- **grid 的边框**

	- borderWidth : 10

- **grid 的位置和大小**

	- left top right bottom

	- width height

```js
var option = {
	grid: {
		show: true, // 显示grid
		borderWidth: 10, // grid的边框宽度
		borderColor: 'red', // grid的边框颜色
		left: 100, // grid的位置
		top: 100,
		width: 300, // grid的大小
		height: 150
	}
}
```



<font color='red'>配置2: 坐标轴 axis</font>

坐标轴分为x轴和y轴, 一个 grid 中最多有两种位置的 x 轴和 y 轴

- **坐标轴类型 type**

	- value : 数值轴, 自动会从目标数据中读取数据

	- category : 类目轴, 该类型必须通过 data 设置类目数据

- **坐标轴位置**

	- xAxis : 可取值为 top 或者 bottom

	- yAxis : 可取值为 left 或者 right

```js
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr,
		position: 'top'
	},
	yAxis: {
		type: 'value',
		position: 'right'
	}
}
```



<font color='red'>配置3: 区域缩放 dataZoom</font>

dataZoom 用于区域缩放, 对数据范围过滤, x轴和y轴都可以拥有, dataZoom 是一个数组, 意味着可以配置多个区域缩放器

- **区域缩放类型 type**
	- slider : 滑块
	- inside : 内置, 依靠鼠标滚轮或者双指缩放

- **产生作用的轴**

	- xAxisIndex :设置缩放组件控制的是哪个 x 轴, 一般写0即可
	- yAxisIndex :设置缩放组件控制的是哪个 y 轴, 一般写0即可

	

- **指明初始状态的缩放情况**

	- start : 数据窗口范围的起始百分比
	- end : 数据窗口范围的结束百分比

```js
var option = {
	xAxis: {
		type: 'category',
		data: xDataArr
	},
	yAxis: {
		type: 'value'
	},
	dataZoom: [
		{
			type: 'slider',
			xAxisIndex: 0
		},
		{
			type: 'slider',
			yAxisIndex: 0,
			start: 0,
			end: 80
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818220135237.png" alt="image-20250818220135237" style="zoom:50%;" />

需要注意的是, 针对于非直角坐标系图表, 比如饼图 地图 等, 以上三个配置可能就不会生效了



## 3.4.图表4 饼图



### 3.4.1.饼图的实现步骤



- **步骤1 ECharts 最基本的代码结构**

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<script src="js/echarts.min.js"></script>
</head>
<body>
	<div style="width: 600px;height:400px"></div>
	<script>
		var mCharts = echarts.init(document.querySelector("div"))
		var option = {}
		mCharts.setOption(option)
	</script>
</body>
</html>
```

此时 option 是一个空空如也的对象

- **步骤2 准备数据**

```js
var pieData = [
	{
		value: 11231,
		name: "淘宝",
	},
	{
		value: 22673,
		name: "京东"
	},
	{
		value: 6123,
		name: "唯品会"
	},
	{
		value: 8989,
		name: "1号店"
	},
	{
		value: 6700,
		name: "聚美优品"
	}
]
```

- **步骤3 准备配置项 在 series 下设置 type:pie**

```js
var option = {
	series: [
		{
			type: 'pie',
			data: pieData
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818220401707.png" alt="image-20250818220401707" style="zoom:50%;" />

注意:

- 饼图的数据是由 name 和 value 组成的字典所形成的数组
- 饼图无须配置 xAxis 和 yAxis



### 3.4.2.饼图的常见效果



- **显示数值**
	- label.show : 显示文字
	- label.formatter : 格式化文字

```js
var option = {
	series: [
		{
			type: 'pie',
			data: pieData,
			label: {
				show: true,
				formatter: function (arg) {
				return arg.data.name + '平台' + arg.data.value + '元\n' + arg.percent + '%'
				}
			}
		}
	]
}
```





- **南丁格尔图**

	南丁格尔图指的是每一个扇形的半径随着数据的大小而不同, 数值占比越大, 扇形的半径也就越大

	- roseType:'radius'

```js
var option = {
	series: [
		{
			type: 'pie',
			data: pieData,
			label: {
				show: true,
				formatter: function (arg) {
					return arg.data.name + '平台' + arg.data.value + '元\n' + arg.percent + '%'
				}
			},
			roseType: 'radius'
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818220731439.png" alt="image-20250818220731439" style="zoom:50%;" />

- **选中效果**

	- selectedMode: 'multiple'

		选中模式，表示是否支持多个选中，默认关闭，支持布尔值和字符串，字符串取值可

		选 'single' ， 'multiple' ，分别表示单选还是多选

	- selectedOffset: 30

		选中扇区的偏移距离

```js
var option = {
	series: [
		{
			type: 'pie',
			data: pieData,
			selectedMode: 'multiple', //
			selectedOffset: 30
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818220832675.png" alt="image-20250818220832675" style="zoom:50%;" />

- **圆环**

	- radius

		饼图的半径。可以为如下类型：

		number ：直接指定外半径值。 

		string ：例如， '20%' ，表示外半径为可视区尺寸（容器高宽中较小一项）的 20% 长度。 

		Array ：数组的第一项是内半径，第二项是外半径, 通过 Array , 可以将饼图设置为圆环图

```js
var option = {
	series: [
		{
			type: 'pie',
			data: pieData,
			radius: ['50%', '70%']
		}
	]
}
```

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250818221015457.png" alt="image-20250818221015457" style="zoom:50%;" />



### 3.4.3.饼图的特点

饼图可以很好地帮助用户快速了解不同分类的数据的<font color='red'>占比情况</font>



