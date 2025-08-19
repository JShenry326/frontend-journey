# 1、CSS简介



> CSS 的主要使用场景就是美化网页,布局页面的



## 1.1 HTML 的局限性



说起 HTML，这其实是个非常单纯的家伙，他<font color='red'>只关注内容的语义</font>。比如`<h1>`> 表明这是一个大标题，`<p>`表明这是一个段落，`<img>` 表

明这儿有一个图片，`<a>` 表示此处有链接。

很早的时候，世界上的网站虽然很多，但是他们都有一个共同的特点：<font color='red'>丑</font>。

虽然 HTML 可以做简单的样式，但是带来的是无尽的<font color='red'>臃肿和繁琐</font>……



## 1.2 CSS-网页的美容师



<font color='red'>**CSS** </font>是<font color='red'>层叠样式表 </font>( <font color='red'>Cascading Style Sheets</font> ) 的简称.

有时我们也会称之为<font color='red'> CSS 样式表</font>或<font color='red'>级联样式表</font>。

CSS 是也是一种标记语言

CSS 主要用于设置 HTML 页面中的<font color='red'>文本内容</font>（字体、大小、对齐方式等）、<font color='red'>图片的外形</font>（宽高、边框样式、边距等）以及<font color='red'>版面的布局和外观显示样式</font>。

CSS 让我们的网页更加丰富多彩，布局更加灵活自如。简单理解：<font color='red'>CSS 可以美化 HTML , 让 HTML 更漂亮，让页面布局更简单</font>。

![image-20240911203044840](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240911203044840.png)

> 总结:

1. HTML 主要做结构,显示元素内容.
2. CSS 美化 HTML ,布局网页.
3. **CSS 最大价值:** **由 HTML 专注去做结构呈现，样式交给 CSS，即 结构 ( HTML ) 与样式( CSS ) 相分离。**



## 1.3 CSS 语法规范



使用 HTML 时，需要遵从一定的规范，CSS 也是如此。要想熟练地使用 CSS 对网页进行修饰，首先需要了解CSS 样式规则。

<font color='red'>CSS 规则由两个主要的部分构成：选择器以及一条或多条声明。</font>

![image-20240911203200794](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240911203200794.png)

- <font color='red'>选择器</font>是用于指定 CSS 样式的 <font color='red'>HTML 标签</font>，花括号内是对该对象设置的具体样式
- 属性和属性值以“<font color='red'>键值对</font>”的形式出现
- 属性是对指定的对象设置的样式属性，例如字体大小、文本颜色等
- 属性和属性值之间用英文“<font color='red'>:</font>”分开
- 多个“键值对”之间用英文“<font color='red'>;</font>”进行区分



所有的样式，都包含在` <style> `标签内，表示是样式表。`<style>` 一般写到 `</head>` 上方。

```
<head>
 	<style>
 		h4 {
 			color: blue;
 			font-size: 100px;
		 }
 	</style>
</head>
```



## 1.4 CSS 代码风格



> 以下代码书写风格不是强制规范,而是符合实际开发书写方式.
>
> 1. **样式格式书写**
> 2. **样式大小写风格**
> 3. **样式空格风格**



### 1. 样式格式书写



#### ① 紧凑格式

```
h3 { color: deeppink;font-size: 20px;}
```



#### ② 展开格式

```
h3 {
 	color: pink;
 	font-size: 20px; 
}
```

<font color='red'>强烈推荐第二种格式</font>， 因为更直观。



### 2. 样式大小写



```
h3 {
 color: pink;
}
```

```
H3 {
 COLOR: PINK; 
}
```

<font color='red'>强烈推荐样式选择器，属性名，属性值关键字**全部使用小写字母**</font>，特殊情况除外。



### 3. 空格规范



```
h3 {
 	color: pink; 
}
```

1. 属性值前面，冒号后面，保留一个空格
2. 选择器（标签）和大括号中间保留空格



# 2. CSS基础选择器



## 2.1 CSS 选择器的作用



```
<div>我是div</div>
<div>我是div</div>
<p>我是段落</p>
<ul>
 	<li>我是ul里面小li哦</li>
</ul>
<ol>
 	<li>我是ol里面小li哦</li>
</ol> 
```

> 1. 我想把 div 里面的文字改为红色? 
> 2. 我想把第一个div 里面的文字改为红色?
> 3. 我想把ul 里面的 li 文字改为红色



选择器(选择符)就是根据不同需求把不同的标签选出来这就是选择器的作用。 简单来说，就是<font color='red'>选择标签用的</font>。

![image-20240911204053893](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240911204053893.png)

以上 CSS 做了两件事：
1. 找到所有的 h1 标签。 选择器（选对人）。
2. 设置这些标签的样式，比如颜色为红色（做对事）。



## 2.2 选择器分类



<font color='red'>**选择器**</font>分为<font color='red'>基础选择器</font>和<font color='red'>复合选择器</font>两个大类，我们这里先讲解一下基础选择器。

- 基础选择器是由<font color='red'>单个选择器</font>组成的
- 基础选择器又包括：<font color='red'>标签选择器</font>、<font color='red'>类选择器</font>、<font color='red'>id 选择器</font>和<font color='red'>通配符选择器</font>。



## 2.3 标签选择器



<font color='red'>标签选择器</font>（元素选择器）是指用<font color='red'> HTML 标签名称</font>作为选择器，按标签名称分类，为页面中某一类标签指定统一的 CSS 样式。



> **语法**

```
标签名{
 	属性1: 属性值1; 
 	属性2: 属性值2; 
 	属性3: 属性值3; 
 	...
} 
```



> **作用**

标签选择器可以把某一类标签全部选择出来，比如所有的 `<div>`标签和所有的` <span> `标签。



> **优点**

能快速为页面中同类型的标签统一设置样式。



> **缺点**

不能设计差异化样式，只能选择全部的当前标签



## 2.4 类选择器



如果想要差异化选择不同的标签，单独选一个或者某几个标签，可以使用<font color='red'>类选择器</font>.

类选择器在 HTML 中以 <font color='red'>class </font>属性表示，在 CSS 中，类选择器以一个点“.”号显示。



> **语法**

```
.类名 {
 	属性1: 属性值1; 
 	...
}
```

例如，将所有拥有 red 类的 HTML 元素均为红色。

```
.red {
 	color: red;
}
```



> 结构需要用**class属性**来调用 class 类的意思

```
<div class=‘red’> 变红色 </div>
```



> **注意**

1. 类选择器使用“.”（英文点号）进行标识，后面紧跟类名（自定义，我们自己命名的）。
2. 可以理解为给这个标签起了一个名字，来表示。
3. 长名称或词组可以使用中横线来为选择器命名。
4. 不要使用纯数字、中文等命名，尽量使用英文字母来表示。
5. 命名要有意义，尽量使别人一眼就知道这个类名的目的。
6. 命名规范：见附件（ Web 前端开发规范手册.doc）



**<font color='red'>记忆口诀</font>**：样式<font color='red'>点</font>定义，结构<font color='red'>类</font>调用。一个或多个，开发最常用。



### 2.4 类选择器-多类名



我们可以给一个标签指定<font color='red'>多个类名</font>，从而达到更多的选择目的。 这些类名都可以选出这个标签.

简单理解就是一个标签有多个名字. 

![image-20240911205306781](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240911205306781.png)



> 1. 多类名使用方式
> 2. 多类名开发中使用场景



#### 1.多类名使用方式



```
<div class="red font20">亚瑟</div>
```



(1) 在标签class 属性中写 多个类名

(2) 多个类名中间必须用空格分开

(3) 这个标签就可以分别具有这些类名的样式



#### 2.多类名开发中使用场景



(1) 可以把一些标签元素相同的样式(共同的部分)放到一个类里面.

(2) 这些标签都可以调用这个公共的类,然后再调用自己独有的类.

(3) 从而节省CSS代码,统一修改也非常方便



> 示例

```
<div class="pink fontWeight font20">亚瑟</div>
<div class="font20">刘备</div>
<div class="font14 pink">安其拉</div>
<div class="font14">貂蝉</div>
```



- 各个类名中间用空格隔开
- 简单理解：就是给某个标签添加了多个类，或者这个标签有多个名字
- 这个标签就可以分别具有这些类名的样式
- 从而节省CSS代码,统一修改也非常方便.
- 多类名选择器在后期布局比较复杂的情况下，还是较多使用的



## 2.5 id 选择器



id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。

HTML 元素以<font color='red'> id 属性</font>来设置 id 选择器，CSS 中 id 选择器以“<font color='red'>#</font>" 来定义。



> 语法

```
#id名 {
 	属性1: 属性值1; 
 	...
}
```

例如，将 id 为 nav 元素中的内容设置为红色。

```
#nav {
 	color:red;
}
```

<font color='red'>注意：id 属性只能在每个 HTML 文档中出现一次。口诀: 样式#定义,结构id调用, 只能调用一次, 别人切勿使用.</font>



> **id 选择器和类选择器的区别**

1. 类选择器（class）好比人的名字，一个人可以有多个名字，同时一个名字也可以被多个人使用。
2. id 选择器好比人的身份证号码，全中国是唯一的，不得重复。
3.  id 选择器和类选择器最大的不同在于使用次数上。
4. 类选择器在修改样式中用的最多，id 选择器一般用于页面唯一性的元素上，经常和 JavaScript 搭配使用。



## 2.6 通配符选择器



在 CSS 中，通配符选择器使用“<font color='red'>*</font>”定义，它表示选取页面中所有元素（标签）。



> 语法

```
* {
 	属性1: 属性值1; 
 	...
} 
```

- 通配符选择器不需要调用， 自动就给所有的元素使用样式
- 特殊情况才使用，后面讲解使用场景(以下是清除所有的元素标签的内外边距,后期讲)

```
* {
	 margin: 0;
	 padding: 0;
}
```



## 2.7 基础选择器总结



| 基础选择器   | 作用                          | 特点                               | 使用情况     | 用法               |
| ------------ | ----------------------------- | ---------------------------------- | ------------ | ------------------ |
| 标签选择器   | 可以选出所有相同的标签，比如p | 不能差异化选择                     | 较多         | p {color: red;}    |
| 类选择器     | 可以选出1个或者多个标签       | 可以根据需求选择                   | 非常多       | .nav {color: red;} |
| id选择器     | 一次只能选择1个标签           | ID属性只能在每个HTML文档中出现一次 | 一般和js搭配 | #nav {color: red;} |
| 通配符选择器 | 选择所有的标签                | 选择的太多，有部分不需要           | 特殊情况使用 | * {color: red;}    |

- 每个基础选择器都有使用场景，都需要掌握
- 如果是修改样式， 类选择器是使用最多的



# 3. CSS 字体属性



> CSS Fonts (字体)属性用于定义字体系列、大小、粗细、和文字样式（如斜体）。



## 3.1 字体系列



> CSS 使用 <font color='red'>font-family</font> 属性定义文本的字体系列。

```
p { font-family:"微软雅黑";} 
div {font-family: Arial,"Microsoft Yahei", "微软雅黑";}
```

- 各种字体之间必须使用英文状态下的逗号隔开
- 一般情况下,如果有空格隔开的多个单词组成的字体,加引号.
- 尽量使用系统默认自带字体，保证在任何用户的浏览器中都能正确显示
- 最常见的几个字体：body {font-family: 'Microsoft YaHei',tahoma,arial,'Hiragino Sans GB'; }



## 3.2 字体大小



> CSS 使用 <font color='red'>font-size</font> 属性定义字体大小。

```
p { 
 	font-size: 20px; 
}
```

- px（像素）大小是我们网页的最常用的单位
- 谷歌浏览器默认的文字大小为16px
- 不同浏览器可能默认显示的字号大小不一致，我们尽量给一个明确值大小，不要默认大小
- 可以给 body 指定整个页面文字的大小



## 3.3 字体粗细



> CSS 使用<font color='red'> font-weight</font> 属性设置文本字体的粗细。

```
p { 
 	font-weight: bold;
}
```

| 属性值  | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| normal  | 默认值（不加粗）                                             |
| bold    | 定义粗体（加粗的）                                           |
| 100-900 | 400等同于normal（不加粗），而700等同于bold（加粗），注意这个数字后面不跟单位 |

- 学会让加粗标签（比如 h 和 strong 等) 不加粗，或者其他标签加粗
- <font color='red'>实际开发时，我们更喜欢用数字表示粗细</font>



## 3.4 文字样式



> CSS 使用<font color='red'> font-style </font>属性设置文本的风格。

```
p { 
	 font-style: normal;
}
```

| 属性值 | 作用                                                   |
| ------ | ------------------------------------------------------ |
| normal | 默认值，浏览器会显示标准的字体样式 font-style: normal; |
| italic | 浏览器会显示斜体的字体样式                             |

<font color='red'>**注意**： 平时我们很少给文字加斜体，反而要给斜体标签（em，i）改为不倾斜字体。</font>



## 3.5 字体复合属性



字体属性可以把以上文字样式综合来写, 这样可以更节约代码：

```
body { 
 	font: font-style font-weight font-size/line-height font-family;
}
```

- 使用 font 属性时，必须按上面语法格式中的顺序书写，<font color='red'>不能更换顺序</font>，并且各个属性间以<font color='red'>空格</font>隔开
- 不需要设置的属性可以省略（取默认值），但<font color='red'>必须保留 font-size 和 font-family 属性</font>，否则 font 属性将不起作用



## 3.6 字体属性总结



| 属性        | 表示     | 注意点                                                       |
| ----------- | -------- | ------------------------------------------------------------ |
| font-size   | 字号     | 我们通常用的单位是px像素，一定要跟上单位                     |
| font-family | 字体     | 实际工作中按照团队约定来写字体                               |
| font-weight | 字体粗细 | 记住加粗是 700 或者 bold ，不加粗是 normal 或者 400 ，记住数字不要跟单位 |
| font-style  | 字体样式 | 记住倾斜是 italic ，不倾斜是 normal ，工作中我们最常用 normal |
| font        | 字体连写 | 1.字体连写是有顺序的，不能随意换位置 2.其中字号和字体必须同时出现 |



# 4. CSS文本属性



> CSS Text（文本）属性可定义文本的外观，比如文本的颜色、对齐文本、装饰文本、文本缩进、行间距等。



## 4.1 文本颜色



<font color='red'>color </font>属性用于定义文本的颜色。

```
div { 
 	color: red;
}
```

| 表示方式       | 属性值                        |
| -------------- | ----------------------------- |
| 预定义的颜色值 | red,green,blue,pink等         |
| 十六进制       | #FF0000,#FF6600,#29D794等     |
| RGB代码        | rgb(255,0,0)或rgb(100%,0%,0%) |

<font color='red'>开发中最常用的是十六进制.</font>



## 4.2 对齐文本



<font color='red'>text-align</font> 属性用于设置元素内文本内容的水平对齐方式。

```
div { 
 	text-align: center;
}
```

| 属性值 | 解释           |
| ------ | -------------- |
| left   | 左对齐（默认） |
| right  | 右对齐         |
| center | 居中对齐       |



## 4.3 装饰文本



<font color='red'>text-decoration</font> 属性规定添加到文本的修饰。可以给文本添加下划线、删除线、上划线等。

```
div { 
 	text-decoration：underline；
}
```

| 属性值       | 描述                              |
| ------------ | --------------------------------- |
| none         | 默认。没有装饰线（最常用）        |
| underline    | 下划线。链接 a 自带下划线（常用） |
| overline     | 上划线。（几乎不用）              |
| line-through | 删除线。（不常用）                |

<font color='red'>pink 老师总结: 重点记住如何添加下划线 ? 如何删除下划线 ? 其余了解即可.</font>



## 4.4 文本缩进



<font color='red'>text-indent </font>属性用来指定文本的第一行的缩进，通常是将<font color='red'>段落的首行缩进</font>。

![image-20240914174505639](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240914174505639.png)

```
div { 
 	text-indent: 10px;
}
```

通过设置该属性，所有元素的第一行都可以缩进一个给定的长度，甚至该长度可以是负值。

```
p { 
 	text-indent: 2em;
}
```

<font color='red'>em</font> 是一个相对单位，就是当前元素（font-size) <font color='red'>1 个文字的大小</font>, 如果当前元素没有设置大小，则会按照父元素的 1 个文字大小。



## 4.5 行间距



<font color='red'>line-height </font>属性用于设置行间的距离（行高）。可以控制文字行与行之间的距离.

```
p { 
 	line-height: 26px;
}
```

![image-20240914174712273](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240914174712273.png)



## 4.6 去除li前面的项目符号（小圆点）



> 语法：

```
list-style: none; 
```



## 4.7 文本属性总结



| 属性            | 表示     | 注意点                                                  |
| --------------- | -------- | ------------------------------------------------------- |
| color           | 文本颜色 | 我们通常用十六进制，比如#FF0000，而且通常是简写形式#fff |
| text-align      | 文本对齐 | 可以设定文字水平的对齐方式                              |
| text-indent     | 文本缩进 | 通常我们用于段落首行缩进2个字的距离 text-indent:2em;    |
| text-decoration | 文本修饰 | 记住 添加下划线 underline 取消下划线 none               |
| line-height     | 行高     | 控制行与行之间的距离                                    |



# 5. CSS的引入方式



## 5.1 CSS的三种样式表



按照 CSS 样式书写的位置（或者引入的方式），CSS 样式表可以分为三大类：
1. 行内样式表（行内式）
2. 内部样式表（嵌入式）
3. 外部样式表（链接式）



## 5.2 内部样式表



内部样式表（内嵌样式表）是写到html页面内部. 是将所有的 CSS 代码抽取出来，单独放到一个` <style>` 标签中。

```
<style>
 	div {
 		color: red;
 		font-size: 12px;
 	}
</style>
```

- `<style>`标签理论上可以放在 HTML 文档的任何地方，但一般会放在文档的`<head>`标签中
- 通过此种方式，可以方便控制当前整个页面中的元素样式设置
- 代码结构清晰，但是并没有实现结构与样式完全分离
- 使用内部样式表设定 CSS，通常也被称为<font color='red'>嵌入式引入</font>，这种方式是我们练习时常用的方式



## 5.3 行内样式表



行内样式表（内联样式表）是<font color='red'>在元素标签内部的 style 属性中设定 CSS 样式</font>。适合于修改简单样式.

```
<div style="color: red; font-size: 12px;">青春不常在，抓紧谈恋爱</div>
```

- style 其实就是标签的属性
- 在双引号中间，写法要符合 CSS 规范
- 可以控制当前的标签设置样式
- 由于书写繁琐，并且没有体现出结构与样式相分离的思想，所以不推荐大量使用，只有对当前元素添加简单样式的时候，可以考虑使用
- 使用行内样式表设定 CSS，通常也被称为<font color='red'>行内式引入</font>



## 5.4 外部样式表



> 实际开发都是外部样式表. 适合于样式比较多的情况. 核心是:样式单独写到CSS 文件中，之后把CSS文件引入到 HTML 页面中使用.

引入外部样式表分为两步：
1. 新建一个后缀名为 .css 的样式文件，把所有 CSS 代码都放入此文件中。
2. 在 HTML 页面中，使用``<link>`` 标签引入这个文件。

```
<link rel="stylesheet" href="css文件路径">
```

| 属性 | 作用                                                         |
| ---- | ------------------------------------------------------------ |
| rel  | 定义当前文档与被链接文档之间的关系，在这里需要指定为“stylesheet”，表示被链接文档是一个样式表文件 |
| href | 定义所链接外部样式表文件的url，可以是相对路径，也可以是绝对路径 |

- 使用外部样式表设定 CSS，通常也被称为<font color='red'>外链式</font>或<font color='red'>链接式引入</font>，这种方式是开发中常用的方式



## 5.5 引入方式总结



| 样式表     | 优点                     | 缺点         | 使用情况       | 控制范围     |
| ---------- | ------------------------ | ------------ | -------------- | ------------ |
| 行内样式表 | 书写方便，权重高         | 结构样式混写 | 较少           | 控制一个标签 |
| 内部样式表 | 部分结构和样式相分离     | 没有彻底分离 | 较多           | 控制一个页面 |
| 外部样式表 | 完全实现结构和样式相分离 | 需要引入     | 最多，吐血推荐 | 控制多个页面 |



# 6. Chrome调试工具



Chrome 浏览器提供了一个非常好用的调试工具，可以用来调试我们的 HTML 结构和 CSS 样式。



## 6.1 打开调试工具



打开 Chrome 浏览器，按下 <font color='red'>F12 键</font>或者<font color='red'>右击页面空白处→检查</font>。

![image-20240918152201468](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240918152201468.png)



## 6.2 使用调试工具



1. <font color='red'>Ctrl+滚轮</font> 可以放大开发者工具代码大小。
2. 左边是 HTML 元素结构，右边是 CSS 样式。
3. 右边 CSS 样式可以改动数值（左右箭头或者直接输入）和查看颜色。
4. <font color='red'>Ctrl + 0</font> 复原浏览器大小。
5. 如果点击元素，发现右侧没有样式引入，极有可能是类名或者样式引入错误。
6. 如果有样式，但是样式前面有<font color='red'>黄色叹号提示</font>，则是样式属性书写错误。



# 7. Emmet语法



> Emmet语法的前身是Zen coding,它使用缩写,来提高html/css的编写速度, Vscode内部已经集成该语法.



## 7.1 快速生成HTML结构语法



1. 生成标签 直接输入标签名 按tab键即可 比如 div 然后tab 键， 就可以生成 `<div></div>`
2. 如果想要生成多个相同标签 加上 * 就可以了 比如 div*3 就可以快速生成3个div
3. 如果有父子级关系的标签，可以用 > 比如 ul > li就可以了
4. 如果有兄弟关系的标签，用 + 就可以了 比如 div+p 
5. 如果生成带有类名或者id名字的， 直接写 .demo 或者 #two tab 键就可以了
6. 如果生成的div 类名是有顺序的， 可以用 自增符号 $ 
7. 如果想要在生成的标签内部写内容可以用 { } 表示



## 7.2 快速生成CSS样式语法



CSS 基本采取简写形式即可.
1. 比如 w200 按tab 可以 生成 width: 200px;
2. 比如 lh26px 按tab 可以生成 line-height: 26px;



## 7.3 快速格式化代码



Vscode 快速格式化代码: shift+alt+f

也可以设置 当我们 保存页面的时候自动格式化代码:

1）文件 ------.>【首选项】---------->【设置】；

2）搜索emmet.include;

3）在settings.json下的【工作区设置】中添加以下语句：

"editor.formatOnType": true,
"editor.formatOnSave": true



# 8. CSS的复合选择器



## 8.1 什么是复合选择器



在 CSS 中，可以根据选择器的类型把选择器分为<font color='red'>基础选择器</font>和<font color='red'>复合选择器</font>，复合选择器是建立在基础选择器之上，对基本选择器进行组合形成的。

- 复合选择器可以更准确、更高效的选择目标元素（标签）
- 复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的
- 常用的复合选择器包括：后代选择器、子选择器、并集选择器、伪类选择器等等



## 8.2 后代选择器（重要）



**<font color='red'>后代选择器</font>**又称为<font color='red'>包含选择器</font>，可以选择父元素里面子元素。其写法就是把外层标签写在前面，内层标签写在后面，中间用空格分隔。当标签发生嵌套时，内层标签就成为外层标签的后代。



> 语法：

```
元素1 元素2 { 样式声明 } 
```

上述语法表示<font color='red'>选择元素 1 里面的所有元素 2 </font>(后代元素)。

> 例如：

```
ul li { 样式声明 } /* 选择 ul 里面所有的 li标签元素 */
```



- 元素1 和 元素2 中间用<font color='red'>**空格隔开**</font>
- 元素1 是父级，元素2 是子级，最终选择的是**<font color='red'>元素2</font>**
- 元素2 可以是儿子，也可以是孙子等，只要是元素1 的后代即可
- 元素1 和 元素2 可以是任意基础选择器



## 8.3 子选择器（重要）



<font color='red'>子元素选择器（子选择器）</font>只能选择作为某元素的最近一级子元素。简单理解就是选亲儿子元素.



> 语法：

```
元素1 > 元素2 { 样式声明 } 
```

上述语法表示<font color='red'>选择元素1 里面的所有直接后代(子元素) 元素2</font>。

> 例如：

```
div > p { 样式声明 } /* 选择 div 里面所有最近一级 p 标签元素 */
```



- 元素1 和 元素2 中间用 <font color='red'>**大于号**</font> 隔开
- 元素1 是父级，元素2 是子级，<font color='red'>最终选择的是**元素2**</font>
- 元素2 必须是<font color='red'>**亲儿子**</font>，其孙子、重孙之类都不归他管. 你也可以叫他 亲儿子选择器



## 8.4 并集选择器（重要）



<font color='red'>并集选择器可以选择多组标签, 同时为他们定义相同的样式</font>。通常用于集体声明.

<font color='red'>**并集选择器**</font>是各选择器<font color='red'>通过英文逗号（,）连接而成</font>，任何形式的选择器都可以作为并集选择器的一部分。



> 语法：

```
元素1,元素2 { 样式声明 } 
```

上述语法表示<font color='red'>选择元素1 和 元素2</font>。

> 例如:

```
ul,div { 样式声明 } /* 选择 ul 和 div标签元素 */ 
```



- 元素1 和 元素2 中间用<font color='red'>逗号隔开</font>
- 逗号可以理解为<font color='red'>和</font>的意思
- 并集选择器通常用于集体声明



## 8.5 伪类选择器



<font color='red'>伪类选择器</font>用于向某些选择器添加特殊的效果，比如给链接添加特殊效果，或选择第1个，第n个元素。

伪类选择器书写最大的特点是<font color='red'>用冒号（:）表示</font>，比如 :hover 、 :first-child 。

因为伪类选择器很多，比如有链接伪类、结构伪类等，所以这里先给大家讲解常用的链接伪类选择器。



## 8.6 链接伪类选择器



<font color='red'>**链接伪类选择器注意事项**</font>

1. 为了确保生效，请按照<font color='red'> LVHA </font>的循顺序声明 :link（未被访问过的链接）－:visited（访问过的链接）－:hover（鼠标放置于链接上方时）－:active（鼠标点击链接发送的变化）。
2. 记忆法：love hate 或者 lv 包包 hao 。
3. 因为 a 链接在浏览器中具有默认样式，所以我们实际工作中都需要给链接单独指定样式。



**<font color='red'>链接伪类选择器实际工作开发中的写法：</font>**

```
 /* a 是标签选择器 所有的链接 */ 
 a { 
 color: gray;
 }
 /* :hover 是链接伪类选择器 鼠标经过 */
 a:hover { 
 color: red; /* 鼠标经过的时候，由原来的 灰色 变成了红色 */
 } 
```



## 8.7  :focus 伪类选择器



<font color='red'>:focus 伪类选择器</font>用于选取获得焦点的表单元素。

焦点就是光标，一般情况 `<input>`类表单元素才能获取，因此这个选择器也主要针对于表单元素来说。

```
input:focus { 
 	background-color:yellow;
}
```

> 效果：鼠标选中的表单元素（例如文本框）将会按照设定值进行变化

若设置完发现样式外围附着着一圈黑框（浏览器默认自带），使用`outline:none`可去除这圈黑框。

## 8.8 复合选择器总结



| 选择器         | 作用                   | 特征             | 使用情况 | 隔开符号及用法                         |
| -------------- | ---------------------- | ---------------- | -------- | -------------------------------------- |
| 后代选择器     | 用来选择后代元素       | 可以是子孙后代   | 较多     | 符号是**空格** .nav a                  |
| 子代选择器     | 选择最近一级元素       | 只选亲儿子       | 较少     | 符号是**大于** .nav>p                  |
| 并集选择器     | 选择某些相同样式的元素 | 可以用于集体声明 | 较多     | 符号是**逗号** .nav,.header            |
| 链接伪类选择器 | 选择不同状态的链接     | 跟链接相关       | 较多     | 重点记住 a{} 和 a:hover 实际开发的写法 |
| :focus 选择器  | 选择获取光标的表单     | 跟表单相关       | 较少     | input:focus 记住这个写法               |



# 9. CSS的元素显示模式



> 了解元素的显示模式可以更好的让我们布局页面. 



## 9.1 什么是元素显示模式



> 作用：网页的标签非常多，在不同地方会用到不同类型的标签，了解他们的特点<font color='red'>可以更好的布局我们的网页</font>。

元素显示模式就是<font color='red'>元素（标签）以什么方式进行显示</font>，比如`<div>`自己占一行，比如一行可以放多个``<span>``。



HTML 元素一般分为<font color='red'>块元素</font>和<font color='red'>行内元素</font>两种类型。



## 9.2 块元素



常见的块元素有`<h1>~<h6>、<P>、<div>、<ul>、<ol>、<li>`等，其中<font color='red'>`<div>`</font>标签是最典型的块元素



**块级元素的特点：**

1. 比较霸道，自己独占一行。
2. 高度，宽度、外边距以及内边距都可以控制。
3. 宽度默认是容器（父级宽度）的100%。
4. 是一个容器及盒子，里面可以放行内或者块级元素



<font color='red'>**注意：**</font>

- 文字类的元素内不能使用块级元素
- `<p>`标签主要用于存放文字，因此 `<p>`里面不能放块级元素，特别是不能放``<div>``
- 同理，`` <h1>~<h6>``等都是文字类块级标签，里面也不能放其他块级元素



## 9.3 行内元素



常见的行内元素有 `<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<ins>、<u>、<span>`等，其中<font color='red'>`<span>`</font>标签是<font color='red'>最典型的行内元素</font>。

有的地方也将行内元素称为<font color='red'>内联元素</font>。



**行内元素的特点：**

1. 相邻行内元素在一行上，一行可以显示多个。
2. 高、宽直接设置是无效的。
3. 默认宽度就是它本身内容的宽度。
4. 行内元素只能容纳文本或其他行内元素。



<font color='red'>**注意：**</font>

- 链接里面不能再放链接
- 特殊情况链接 `<a>` 里面可以放块级元素，但是给 `<a>` 转换一下块级模式最安全



## 9.4 行内块元素



在行内元素中有几个特殊的标签 —— `<img />、<input />、<td>`，它们<font color='red'>同时具有块元素和行内元素的特点</font>。

有些资料称它们为<font color='red'>行内块元素</font>。



**行内块元素的特点：**

1. 和相邻行内元素（行内块）在一行上，但是他们之间会有空白缝隙。一行可以显示多个（行内元素特点）。
2. 默认宽度就是它本身内容的宽度（行内元素特点）。
3. 高度，行高、外边距以及内边距都可以控制（块级元素特点）。



## 9.5 元素显示模式总结



| 元素模式   | 元素排列                 | 设置样式               | 默认宽度         | 包含                     |
| ---------- | ------------------------ | ---------------------- | ---------------- | ------------------------ |
| 块级元素   | 一行只能放一个块级元素   | 可以设置宽度高度       | 容器的100%       | 容器级可以包含任何标签   |
| 行内元素   | 一行可以放多个行内元素   | 不可以直接设置宽度高度 | 它本身内容的宽度 | 容纳文本或者其他行内元素 |
| 行内块元素 | 一行可以放多个行内块元素 | 可以设置宽度和高度     | 它本身内容的宽度 |                          |



## 9.6 元素显示模式转换



特殊情况下，我们需要元素模式的转换，简单理解: 一个模式的元素需要另外一种模式的特性

比如想要增加链接 `<a>` 的触发范围。



- <font color='red'>转换为块元素：display:block</font>;
- 转换为行内元素：display:inline;
- <font color='red'>转换为行内块：display: inline-block</font>;



## 9.7 一个小技巧 单行文字垂直居中的代码



CSS 没有给我们提供文字垂直居中的代码. 这里我们可以使用一个小技巧来实现. 

<font color='red'>解决方案</font>: 让文字的行高等于盒子的高度 就可以让文字在当前盒子内垂直居中



## 9.8 单行文字垂直居中的原理



![image-20240918161915245](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240918161915245.png)

**简单理解**: 行高的上空隙和下空隙把文字挤到中间了. 是如果行高小于盒子高度,文字会偏上,如果行高大于盒子高度,则文字偏下



# 10. 一个小工具的使用 snipaste



Snipaste 是一个简单但强大的截图工具，也可以让你将截图贴回到屏幕上. 

**常用快捷方式:**

1. F1 可以截图. 同时测量大小, 设置箭头 书写文字等
2. F3 在桌面置顶显示
3. 点击图片, alt 可以取色 (按下shift 可以切换取色模式)
4. 按下esc 取消图片显示



# 11. CSS的背景



> 通过 CSS 背景属性，可以给页面元素添加背景样式。
>
> 背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等。



## 11.1 背景颜色



<font color='red'>background-color</font> 属性定义了元素的背景颜色

```
background-color:颜色值; 
```



一般情况下元素背景颜色默认值是 <font color='red'>transparent</font>（透明），我们也可以手动指定背景颜色为透明色。

```
background-color:transparent; 
```



## 11.2 背景图片



<font color='red'>background-image</font> 属性描述了元素的背景图像。实际开发常见于 logo 或者一些装饰性的小图片或者是超大的背景图片, 优点是非常便于控制位置. (精灵图也是一种运用场景)

```
background-image : none | url (url) 
```

| 参数值 | 作用                           |
| ------ | ------------------------------ |
| none   | 无背景图（默认的）             |
| url    | 使用绝对或相对地址指定背景图片 |

<font color='red'>注意：背景图片后面的地址，千万不要忘记加 URL， 同时里面的路径不要加引号</font>。



## 11.3 背景平铺



如果需要在 HTML 页面上对背景图像进行平铺，可以使用 <font color='red'>background-repeat </font>属性。

```
background-repeat: repeat | no-repeat | repeat-x | repeat-y
```

| 参数值    | 作用                                 |
| --------- | ------------------------------------ |
| repeat    | 背景图像在纵向和横向上平铺（默认的） |
| no-repeat | 背景图像不平铺                       |
| repeat-x  | 背景图像在横向上平铺                 |
| repeat-y  | 背景图像在纵向上平铺                 |



## 11.4 背景图片位置



利用 <font color='red'>background-position </font>属性可以改变图片在背景中的位置。

```
background-position: x y; 
```

参数代表的意思是：x 坐标和 y 坐标。 可以使用 <font color='red'>方位名词</font> 或者 <font color='red'>精确单位</font>

| 参数值   | 说明                                              |
| -------- | ------------------------------------------------- |
| length   | 百分数\|由浮点数字和单位标识符组成的长度值        |
| position | top\|center\|bottom\|left\|center\|right 方位名词 |



1. 参数是方位名词

- 如果指定的两个值都是方位名词，则两个值前后顺序无关，比如 left top 和 top left 效果一致
- 如果只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐

2. 参数是精确单位

- 如果参数值是精确坐标，那么第一个肯定是 x 坐标，第二个一定是 y 坐标
- 如果只指定一个数值，那该数值一定是 x 坐标，另一个默认垂直居中

3.  参数是混合单位

- 如果指定的两个值是精确单位和方位名词混合使用，则第一个值是 x 坐标，第二个值是 y 坐标



## 11.5 背景图像固定（背景附着）



<font color='red'>background-attachment</font> 属性设置背景图像是否固定或者随着页面的其余部分滚动。

background-attachment 后期可以制作视差滚动的效果

```
background-attachment : scroll | fixed 
```

| 参数   | 作用                       |
| ------ | -------------------------- |
| scroll | 背景图像是随对象内容滚动的 |
| fixed  | 背景图像固定               |



## 11.6 背景复合写法



为了简化背景属性的代码，我们可以将这些属性合并简写在同一个属性 background 中。从而节约代码量.当使用简写属性时，没有特定

的书写顺序,一般习惯约定顺序为：



<font color='red'>background:</font> <font color='orange'>背景颜色</font> <font color='green'>背景图片地址</font> <font color='blue'>背景平铺</font> <font color='pink'>背景图像滚动</font> <font color='purple'>背景图片位置</font>

```
background: transparent url(image.jpg) repeat-y fixed top ;
```



## 11.7 背景色半透明



CSS3 为我们提供了背景颜色半透明的效果。

```
background: rgba(0, 0, 0, 0.3);
```

- 最后一个参数是 alpha 透明度，取值范围在 0~1之间
- 我们习惯把 0.3 的 0 省略掉，写为 background: rgba(0, 0, 0, .3);
- 注意：背景半透明是指盒子背景半透明，盒子里面的内容不受影响
- CSS3 新增属性，是 IE9+ 版本浏览器才支持的
- 但是现在实际开发,我们不太关注兼容性写法了,可以放心使用



## 11.8 背景总结



| 属性                  | 作用           | 值                                               |
| --------------------- | -------------- | ------------------------------------------------ |
| background-color      | 背景颜色       | 预定义的颜色值/十六进制/RGB代码                  |
| background-image      | 背景图片       | url（图片路径）                                  |
| background-repeat     | 是否平铺       | repeat/no-repeat/repeat-x/repeat-y               |
| background-position   | 背景位置       | length/position 分别是x和y坐标                   |
| background-attachment | 背景附着       | scroll（背景滚动）/fixed（背景固定）             |
| 背景简写              | 书写更简单     | 背景颜色 背景图片地址 背景平铺 背景滚动 背景位置 |
| 背景色半透明          | 背景颜色半透明 | background: rgba(0,0,0,0.3); 后面必须是四个值    |

背景图片:实际开发常见于 logo 或者一些装饰性的小图片或者是超大的背景图片, 优点是非常便于控制位置. (精灵图也是一种运用场景)



# 12. CSS的三大特性



> CSS 有三个非常重要的三个特性：层叠性、继承性、优先级。



## 12.1 层叠性



相同选择器给设置相同的样式，此时一个样式就会<font color='red'>覆盖（层叠）</font>另一个冲突的样式。层叠性主要解决样式冲突的问题

层叠性原则：

- 样式冲突，遵循的原则是<font color='red'>就近原则</font>，哪个样式离结构近，就执行哪个样式
- 样式不冲突，不会层叠

![image-20240920174028669](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240920174028669.png)

CSS 层叠性口诀：<font color='red'>长江后浪推前浪，前浪死在沙滩上。</font>



## 12.2 继承性



现实中的继承: 我们继承了父亲的姓

CSS中的继承: 子标签会继承父标签的某些样式，如文本颜色和字号。简单的理解就是：子承父业。

![image-20240920174130045](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240920174130045.png)

- 恰当地使用继承可以简化代码，降低 CSS 样式的复杂性
- 子元素可以继承父元素的样式（text-，font-，line-这些元素开头的可以继承，以及color属性）
- 继承性口诀：<font color='red'>龙生龙，凤生凤，老鼠生的孩子会打洞</font>



**行高的继承性**



```
body {
 font:12px/1.5 Microsoft YaHei；
}
```

- 行高可以跟单位也可以不跟单位
- 如果子元素没有设置行高，则会继承父元素的行高为 1.5
- 此时子元素的行高是：当前子元素的文字大小 * 1.5 
- <font color='red'>body 行高 1.5 这样写法最大的优势就是里面子元素可以根据自己文字大小自动调整行高</font>



## 12.3 优先级



当同一个元素指定多个选择器，就会有优先级的产生。

- 选择器相同，则执行层叠性
- 选择器不同，则根据<font color='red'>选择器权重</font>执行



选择器权重如下表所示。

| 选择器               | 选择器权重 |
| -------------------- | ---------- |
| 继承 或者 *          | 0,0,0,0    |
| 元素选择器           | 0,0,0,1    |
| 类选择器，伪类选择器 | 0,0,1,0    |
| ID选择器             | 0,1,0,0    |
| 行内样式 style=“”    | 1,0,0,0    |
| !important 重要的    | ∞ 无穷大   |



**优先级注意点:**



1. 权重是有4组数字组成,但是不会有进位。
2. 可以理解为类选择器永远大于元素选择器, id选择器永远大于类选择器,以此类推..
3. 等级判断从左向右，如果某一位数值相同，则判断下一位数值。
4. 可以简单记忆法: 通配符和继承权重为0, 标签选择器为1,类(伪类)选择器为 10, id选择器 100, 行内样式表为1000, !important 无穷大.
5. <font color='red'>**继承的权重是0**</font>， 如果该元素没有直接选中，不管父元素权重多高，子元素得到的权重都是 0。



<font color='red'>**权重叠加：**</font>如果是复合选择器，则会有权重叠加，需要计算权重。

- div ul li ------> 0,0,0,3
- .nav ul li ------> 0,0,1,2
- a:hover -----—> 0,0,1,1
- .nav a ------> 0,0,1,1



# 13. 盒子模型



> 页面布局要学习三大核心, 盒子模型, 浮动 和 定位. 学习好盒子模型能非常好的帮助我们布局页面.



## 13.1 看透网页布局的本质



![image-20240922092417917](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922092417917.png)

网页布局过程：
1. 先准备好相关的网页元素，网页元素基本都是盒子 Box 。

2. 利用 CSS 设置好盒子样式，然后摆放到相应位置。

3. 往盒子里面装内容.

  网页布局的核心本质： 就是利用 CSS 摆盒子。



## 13.2 盒子模型（Box Model）组成



![image-20240922092539453](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922092539453.png)

所谓 <font color='red'>盒子模型</font>：就是把 HTML 页面中的布局元素看作是一个矩形的盒子，也就是一个盛装内容的容器。

CSS 盒子模型本质上是一个盒子，封装周围的 HTML 元素，它包括：边框、外边距、内边距、和 实际内容

![image-20240922092622685](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922092622685.png)

![image-20240922092636832](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922092636832.png)



## 13.3 边框（border）



![image-20240922094748163](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922094748163.png)

border可以设置元素的边框。边框有三部分组成:边框宽度(粗细) 边框样式 边框颜色

> 语法：

```
border : border-width || border-style || border-color 
```

| 属性         | 作用                   |
| ------------ | ---------------------- |
| border-width | 定义边框粗细，单位是px |
| border-style | 边框的样式             |
| border-color | 边框颜色               |



CSS 边框属性允许你指定一个元素边框的<font color='red'>样式</font>和<font color='red'>颜色</font>。

> 语法：

```
border : border-width || border-style || border-color 
```

边框样式 border-style 可以设置如下值：

- none：没有边框即忽略所有边框的宽度（默认值）
- solid：边框为单实线(最为常用的)
- dashed：边框为虚线 
- dotted：边框为点线



> 边框简写：

```
border: 1px solid red; 没有顺序 
```



> 边框分开写法：

```
border-top: 1px solid red; /* 只设定上边框， 其余同理 */ 
```



## 13.4 表格的细线边框



> <font color='red'>border-collapse</font> 属性控制浏览器绘制表格边框的方式。它控制相邻单元格的边框。
>
> 表格有边框，单元格也有边框，但相邻单元格的边框拼在一起会变粗，此时就需要边框合并

![image-20240922100518659](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922100518659.png)



> 语法：

```
border-collapse:collapse; 
```

- collapse 单词是合并的意思
- border-collapse: collapse; 表示相邻边框合并在一起



## 13.5 边框会影响盒子实际大小



边框会额外增加盒子的实际大小。因此我们有两种方案解决:
1. 测量盒子大小的时候,不量边框.
2. 如果测量的时候包含了边框,则需要 width/height 减去边框宽度



## 13.6 内边距（padding）



padding 属性用于设置内边距，即边框与内容之间的距离。

| 属性           | 作用     |
| -------------- | -------- |
| padding-left   | 左内边距 |
| padding-right  | 右内边距 |
| padding-top    | 上内边距 |
| padding-bottom | 下内边距 |



<font color='red'>padding</font> 属性（简写属性）可以有一到四个值。

| 值的个数                     | 表达意思                                                   |
| ---------------------------- | ---------------------------------------------------------- |
| padding: 5px;                | 1个值，代表上下左右都有5像素内边距                         |
| padding: 5px 10px;           | 2个值，代表上下内边距是5像素，左右内边距是10像素           |
| padding: 5px 10px 20px;      | 3个值，代表上内边距5像素，左右内边距10像素，下内边距20像素 |
| padding: 5px 10px 20px 30px; | 4个值，代表上5像素，右10像素，下20像素，左30像素，顺时针   |



当我们给盒子指定<font color='red'> padding</font> 值之后，发生了 2 件事情：

1. 内容和边框有了距离，添加了内边距。
2. padding影响了盒子实际大小。

***也就是说，如果盒子已经有了宽度和高度，此时再指定内边框，会撑大盒子。***

***如何盒子本身没有指定width/height属性, 则此时padding不会撑开盒子大小*.**



**解决方案：**

如果保证盒子跟效果图大小保持一致，则让 width/height 减去多出来的内边距大小即可。



**<font color='red'>案例：新浪导航案例-padding影响盒子好处</font>**



padding内边距可以撑开盒子,我们可以做非常巧妙的运用.

因为每个导航栏里面的字数不一样多,我们可以不用给每个盒子宽度了,直接给padding最合适.

![image-20240922102408499](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922102408499.png)



## 13.7 外边距（margin）



<font color='red'>margin </font>属性用于设置外边距，即控制盒子和盒子之间的距离。

| 属性          | 作用     |
| ------------- | -------- |
| margin-left   | 左外边距 |
| margin-right  | 右外边距 |
| margin-top    | 上外边距 |
| margin-bottom | 下外边距 |

margin 简写方式代表的意义跟 padding 完全一致。



###  外边距典型应用



外边距可以让块级盒子<font color='red'>**水平居中**</font>，但是必须满足两个条件：

1. 盒子必须指定了宽度（width）。
2. 盒子<font color='red'>左右的外边距</font>都设置为 auto 。

```
.header{ width:960px; margin:0 auto;}
```

常见的写法，以下三种都可以：

- margin-left: auto; margin-right: auto;
- margin: auto;
- <font color='red'>margin: 0 auto;</font>

<font color='red'>**注意**</font>：以上方法是让<font color='red'>块级元素</font>水平居中，<font color='red'>行内元素或者行内块元素水平居中给其父元素添加 text-align:center 即可</font>。



## 13.8 外边距合并



使用 <font color='red'>margin</font> 定义块元素的<font color='red'>垂直外边距</font>时，可能会出现外边距的合并。

主要有两种情况:

1. 相邻块元素垂直外边距的合并
2. 嵌套块元素垂直外边距的塌



### 1. 相邻块元素垂直外边距的合并



当上下相邻的两个块元素（兄弟关系）相遇时，如果上面的元素有下外边距 margin-bottom，下面的元素有上外边距 margin-top ，则他

们之间的垂直间距不是 margin-bottom 与 margin-top 之和。<font color='red'>取两个值中的较大者这种现象被称为**相邻块元素垂直外边距的合并**</font>。

![image-20240922103242958](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922103242958.png)

**解决方案：**

<font color='red'>尽量只给一个盒子添加 margin 值。</font>



### 2. 嵌套块元素垂直外边距的塌陷



对于两个嵌套关系（父子关系）的块元素，父元素有上外边距同时子元素也有上外边距，此时父元素会塌陷较大的外边距值。

![image-20240922103405621](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922103405621.png)

**解决方案：**

1. 可以为父元素定义上边框。
2. 可以为父元素定义上内边距。
3. 可以为父元素添加 overflow:hidden。

还有其他方法，比如浮动、固定，绝对定位的盒子不会有塌陷问题，后面咱们再总结。



## 13.9 清除内外边距



网页元素很多都带有默认的内外边距，而且不同浏览器默认的也不一致。因此我们在布局前，首先要清除下网页元素的内外边距。

```
* {
 	padding:0; /* 清除内边距 */
 	margin:0; /* 清除外边距 */
 }
```

<font color='red'>**注意**</font>：<font color='red'>行内元素为了照顾兼容性，尽量只设置左右内外边距，不要设置上下内外边距。但是转换为块级和行内块元素就可以了</font>



# 14. PS基本操作



因为网页美工大部分效果图都是利用 <font color='red'>PS（Photoshop）</font>来做的，所以以后我们大部分切图工作都是在 <font color='red'>PS</font> 里面完成。

- <font color='red'>文件→打开 </font>：可以打开我们要测量的图片
- <font color='red'>Ctrl+R</font>：可以打开标尺，或者<font color='red'> 视图→标尺</font>
- 右击标尺，把里面的单位改为<font color='red'>像素 </font>
- <font color='red'>Ctrl+ 加号(+)</font>可以放大视图，<font color='red'> Ctrl+ 减号(-)</font>可以缩小视图
- <font color='red'>按住空格键</font>，鼠标可以变成小手，拖动 PS 视图
- 用<font color='red'>选区</font>拖动 可以测量大小
- <font color='red'>Ctrl+ D</font> 可以取消选区，或者在<font color='red'>旁边空白处点击一下</font>也可以取消选区

![image-20240922103911005](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240922103911005.png)



## PS切图



### 1. 常见的图片格式



1. jpg图像格式： JPEG（.JPG）对色彩的信息保留较好，高清，颜色较多，我们<font color='red'>产品类的图片经常用jpg格式的</font>

2. gif图像格式：GIF格式最多只能储存256色，所以通常用来显示简单图形及字体，但是可以保存透明背景和动画效果, <font color='red'>实际经常用于一些图片小动画效果.</font>
3. png图像格式是一种新兴的网络图形格式，结合了GIF和JPEG的优点，具有存储形式丰富的特点，能够保持透明背景. <font color='red'>如果想要切成背景透明的图片,请选择png格式</font>.
4. PSD图像格式PSD格式是Photoshop的专用格式，里面可以存放图层、通道、遮罩等多种设计稿. <font color='red'>对我们前端人员来说,最大的优点,我们可以直接从上面复制文字,获得图片,还可以测量大小和距离.</font>



> PS 有很多的切图方式：图层切图、切片切图、PS 插件切图等。



### 2. 图层切图



最简单的切图方式：右击图层→快速导出为 PNG。

但是很多情况下,我们需要合并图层再导出:

1. 选中需要的图层: 图层菜单→合并图层(ctrl+e) 
2. 右击→快速导出为 PNG

最好的方法是: 沟通



### 3.切片切图



①利用切片选中图片

​	利用切片工具手动划出

②导出选中的图片

​	文件菜单→导出→存储为 web 设备所用格式→选择我们要的图片格式→存储 。

<font color='red'>一定要把切片选项改为选中的切片！</font>

![image-20241010214520334](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241010214520334.png)



## 像素大厨替代PS





# 15. 问题解惑



Pink 老师总结

1. <font color='red'>布局为啥用不同盒子,我只想用div？</font>

	标签都是有语义的, 合理的地方用合理的标签。比如产品标题 就用 h, 大量文字段落就用p

2. <font color='red'>为啥用辣么多类名？</font>
	类名就是给每个盒子起了一个名字,可以更好的找到这个盒子, 选取盒子更容易,后期维护也方便。

3. <font color='red'>到底用 margin 还是 padding？</font>
	大部分情况两个可以混用，两者各有优缺点，但是根据实际情况，总是有更简单的方法实现。

4. <font color='red'>自己做没有思路？</font>
	布局有很多种实现方式，同学们可以开始先模仿我的写法，然后再做出自己的风格。
	最后同学们一定多运用辅助工具,比如屏幕画笔,ps等等



# 16. 圆角边框



在 CSS3 中，新增了<font color='red'>圆角边框</font>样式，这样我们的盒子就可以变圆角了。<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20240923205343988.png" alt="image-20240923205343988" style="zoom: 50%;" />

<font color='red'>border-radius</font> 属性用于设置元素的外边框圆角。



> 语法：

```
border-radius:length; 
```

- 参数值可以为<font color='red'>数值</font>或<font color='red'>百分比</font>的形式
- 如果是<font color='red'>正方形</font>，想要设置为一个圆，把数值修改为<font color='red'>高度或者宽度的一半</font>即可，或者直接写为 <font color='red'>50%</font>
- 该属性是一个<font color='red'>简写属性</font>，可以跟四个值，分别代表<font color='red'>左上角、右上角、右下角、左下角</font>（顺时针）；
- 若跟两个值，<font color='red'>第一个</font>为<font color='red'>左上角和右下角</font>的数值，<font color='red'>第二个</font>为<font color='red'>右上角和左下角</font>的数值
- 分开写：<font color='red'>border-top-left-radius</font>、<font color='red'>border-top-right-radius</font>、<font color='red'>border-bottom-right-radius</font> 和<font color='red'>border-bottom-left-radius</font>
- <font color='red'>兼容性 ie9+ 浏览器支持, 但是不会影响页面布局,可以放心使用.</font>



# 17. 盒子阴影



CSS3 中新增了盒子阴影，我们可以使用 box-shadow 属性为盒子添加阴影。

> 语法：

```
box-shadow: h-shadow v-shadow blur spread color inset; 
```

| 值       | 描述                                                   |
| -------- | ------------------------------------------------------ |
| h-shadow | 必需。水平阴影的位置。允许负值                         |
| v-shadow | 必需。垂直阴影的位置。允许负值                         |
| blur     | 可选。模糊距离                                         |
| spread   | 可选。阴影的尺寸                                       |
| color    | 可选。阴影的颜色。请参阅CSS颜色值。                    |
| inset    | 可选。将外部阴影（outset）改为内部阴影。默认为外部阴影 |

<font color='red'>注意：</font>

1. 默认的是外阴影(outset), 但是不可以写这个单词,否则造成阴影无效
2. <font color='red'>盒子阴影不占用空间，不会影响其他盒子排列。</font>



# 18. 文字阴影



在 CSS3 中，我们可以使用 <font color='red'>text-shadow </font>属性将阴影应用于文本。

> 语法：

```
text-shadow: h-shadow v-shadow blur color;
```

| 值       | 描述                            |
| -------- | ------------------------------- |
| h-shadow | 必需。水平阴影的位置。允许负值  |
| v-shadow | 必需。垂直阴影的位置。允许负值  |
| blur     | 可选。模糊的距离                |
| color    | 可选。阴影的颜色。参阅CSS颜色值 |



# 19. 浮动



## 19.1 传统网页布局的三种方式



网页布局的本质——用 CSS 来摆放盒子。 把盒子摆放到相应位置.

CSS 提供了三种传统布局方式(简单说,就是盒子如何进行排列顺序：

- 普通流（标准流）
- 浮动
- 定位



## 19.2 标准流（普通流/文档流）



<font color='red'>所谓的标准流: 就是标签按照规定好默认方式排列.</font>



1. 块级元素会独占一行，从上向下顺序排列。

  - 常用元素：div、hr、p、h1~h6、ul、ol、dl、form、table

2. 行内元素会按照顺序，从左到右顺序排列，碰到父元素边缘则自动换行。

  - 常用元素：span、a、i、em 等

  

以上都是标准流布局，我们前面学习的就是标准流，<font color='red'>标准流是最基本的布局方式</font>。

这三种布局方式都是用来摆放盒子的，盒子摆放到合适位置，布局自然就完成了。

<font color='red'>**注意**：实际开发中，一个页面基本都包含了这三种布局方式（后面移动端学习新的布局方式）。</font>



## 19.3 为什么需要浮动？



<font color='red'>提问：我们用标准流能很方便的实现如下效果吗？</font>



**1.如何让多个块级盒子(div)水平排列成一行？**

![image-20241009141941055](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009141941055.png)

比较难，虽然转换为行内块元素可以实现一行显示，但是他们之间会有大的空白缝隙，很难控制。



**2.如何实现两个盒子的左右对齐？**

![image-20241009142116574](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009142116574.png)



<font color='red'>**总结：**</font> 有很多的布局效果，标准流没有办法完成，此时就可以利用浮动完成布局。 因为浮动可以改变元素标签默认的排列方式.

**浮动最典型的应用**：可以让多个块级元素一行内排列显示。

**网页布局第一准则**：<font color='red'>多个块级元素纵向排列找标准流，多个块级元素横向排列找浮动。</font>



## 19.4 什么是浮动？



<font color='red'>float</font> 属性用于创建浮动框，将其移动到一边，直到左边缘或右边缘触及包含块或另一个浮动框的边缘。



> 语法：

```
选择器 { float: 属性值; }
```



| 属性值 | 描述                     |
| ------ | ------------------------ |
| none   | 元素不浮动（**默认值**） |
| left   | 元素向**左**浮动         |
| right  | 元素向**右**浮动         |



## 19.5 浮动特性（重难点）



> 加了浮动之后的元素,会具有很多特性,需要我们掌握的.
>
> 1. <font color='red'>浮动元素会脱离标准流(脱标)</font>
> 2. 浮动的元素会一行内显示并且元素顶部对齐
> 3. 浮动的元素会具有行内块元素的特性



### 设置了浮动（float）的元素最重要特性：



**1. 脱离标准普通流的控制（浮） 移动到指定位置（动）, （俗称<font color='red'>脱标</font>）**

**2. 浮动的盒子<font color='red'>不再保留原先的位置</font>**

![image-20241009142621723](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009142621723.png)



**3. 如果多个盒子都设置了浮动，则它们会按照属性值<font color='red'>一行内显示并且顶端对齐排列</font>。**

![image-20241009142710093](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009142710093.png)

<font color='red'>**注意：** 浮动的元素是互相贴靠在一起的（不会有缝隙），如果父级宽度装不下这些浮动的盒子， 多出的盒子会另起一行对齐。</font>



**4.  浮动元素会具有行内块元素特性。**

任何元素都可以浮动。不管原先是什么模式的元素，添加浮动之后具有<font color='red'>行内块元素</font>相似的特性。

- 如果块级盒子没有设置宽度，默认宽度和父级一样宽，但是添加浮动后，它的大小根据内容来决定
- 浮动的盒子中间是没有缝隙的，是紧挨着一起的
- 行内元素同理



## 19.6 浮动元素经常和标准流父级搭配使用



为了约束浮动元素位置, 我们网页布局一般采取的策略是:

<font color='red'>先用标准流的父元素排列上下位置, 之后内部子元素采取浮动排列左右位置. 符合网页布局第一准则.</font>

![image-20241009143111295](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009143111295.png)

**网页布局第二准则.**

<font color='red'>先设置盒子的大小, 之后设置盒子的位置.</font>



# 20. 常见的网页布局



## 20.1 常见网页布局



![image-20241009143247971](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009143247971.png)

![image-20241009143257224](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009143257224.png)



## 20.2 浮动布局注意点



**1. 浮动和标准流的父盒子搭配。**

<font color='red'>先用标准流的父元素排列上下位置, 之后内部子元素采取浮动排列左右位置</font>



**2.一个元素浮动了，理论上其余的兄弟元素也要浮动。**

一个盒子里面有多个子盒子，如果其中一个盒子浮动了，那么其他兄弟也应该浮动，以防止引起问题。

<font color='red'>浮动的盒子只会影响浮动盒子后面的标准流,不会影响前面的标准流</font>



## 20.3 引入清除浮动：思考题



我们前面浮动元素有一个标准流的父元素, 他们有一个共同的特点,都是有高度的.

但是, 所有的父盒子都必须有高度吗? 



理想中的状态, 让子盒子撑开父亲. 有多少孩子,我父盒子就有多高.

但是不给父盒子高度会有问题吗?…..![image-20241009143611894](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009143611894.png)



# 21. 清除浮动



## 21.1 为什么需要清除浮动？



由于父级盒子很多情况下，不方便给高度，但是子盒子浮动又不占有位置，最后父级盒子高度为 0 时，就会影响下面的标准流盒子。

![image-20241009143715375](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009143715375.png)

- 由于浮动元素不再占用原文档流的位置，所以它会对后面的元素排版产生影响



## 21.2 清除浮动本质



- 清除浮动的本质是清除浮动元素造成的影响
- 如果父盒子本身有高度，则不需要清除浮动
- <font color='red'>清除浮动之后，父级就会根据浮动的子盒子自动检测高度。父级有了高度，就不会影响下面的标准流了</font>



## 21.3 清除浮动的方法



> 语法：

```
选择器{clear:属性值;} 
```

| 属性值 | 描述                                       |
| ------ | ------------------------------------------ |
| left   | 不允许左侧有浮动元素（清除左侧浮动的影响） |
| right  | 不允许右侧有浮动元素（清除右侧浮动的影响） |
| both   | 同时清除左右两侧的浮动的影响               |

我们实际工作中， <font color='red'>几乎只用 clear: both;</font>

<font color='red'>清除浮动的策略是: 闭合浮动</font>





> 1. 额外标签法也称为隔墙法，是 W3C 推荐的做法。
> 2. <font color='red'>父级添加 overflow 属性</font>
> 3. <font color='red'>父级添加after伪元素</font>
> 4. <font color='red'>父级添加双伪元素</font>



### 1.额外标签法



<font color='red'>额外标签法</font>也称为<font color='red'>隔墙法</font>，是 W3C 推荐的做法。

<font color='red'>额外标签法</font>会在浮动元素末尾添加一个空的标签。例如 `<div style="clear:both"></div>`，或者其他标签（如`<br />`等）。

- 优点： 通俗易懂，书写方便
- 缺点： 添加许多无意义的标签，结构化较差

<font color='red'>注意： 要求这个新的空标签必须是块级元素</font>



> 总结：
>
> 1. 清除浮动本质是? 
>     <font color='red'>清除浮动的本质是清除浮动元素脱离标准流造成的影响</font>
> 2. 清除浮动策略是?
>     <font color='red'>闭合浮动. 只让浮动在父盒子内部影响,不影响父盒子外面的其他盒子.</font>
> 3. 额外标签法?
> <font color='red'>隔墙法, 就是在最后一个浮动的子元素后面添加一个额外标签, 添加 清除浮动样式.</font>
> <font color='red'>实际工作可能会遇到,但是不常用</font>



### 2.父级添加 overflow



可以给父级添加<font color='red'> overflow</font> 属性，将其属性值设置为<font color='red'> hidden、 auto</font> 或 <font color='red'>scroll</font> 。

子不教,父之过,注意是给父元素添加代码

-  优点：代码简洁
- 缺点：无法显示溢出的部分



### 3. :after 伪元素法



<font color='red'>:after</font> 方式是额外标签法的升级版。也是给父元素添加

```
.clearfix:after { 
 	content: ""; 
 	display: block; 
 	height: 0; 
 	clear: both; 
 	visibility: hidden; 
} 
.clearfix { /* IE6、7 专有 */ 
 	*zoom: 1;
} 
```

- 优点：没有增加标签，结构更简单
- 缺点：照顾低版本浏览器
- 代表网站： 百度、淘宝网、网易等



### 4.双伪元素清除浮动



也是给父元素添加

```
.clearfix:before,.clearfix:after {
 	content:"";
 	display:table; 
}
.clearfix:after {
 	clear:both;
}
.clearfix {
 	*zoom:1;
} 
```

- 优点：代码更简洁
- 缺点：照顾低版本浏览器
- 代表网站：小米、腾讯等



## 21.4 清除浮动总结



**为什么需要清除浮动？**

1. 父级没高度。
2. 子盒子浮动了。
3. 影响下面布局了，我们就应该清除浮动了。



| 清除浮动的方式        | 优点               | 缺点                               |
| --------------------- | ------------------ | ---------------------------------- |
| 额外标签法（隔墙法）  | 通俗易懂，书写方便 | 添加许多无意义的标签，结构化较差   |
| 父级 overflow:hidden; | 书写简单           | 溢出隐藏                           |
| 父级 after 伪元素     | 结构语义化正确     | 由于IE6-7不支持 :after，兼容性问题 |
| 父级双伪元素          | 结构语义化正确     | 由于IE6-7不支持 :after，兼容性问题 |



------



# <font color='red'>学成在线案例</font>



![image-20241009153405750](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009153405750.png)



## 1 准备素材和工具



1. 学成在线 PSD 源文件。

2. 开发工具 = PS（切图） + sublime（代码） + chrome（测试）。



## 2 案例准备工作



我们本次采取结构与样式相分离思想：
1. 创建 study 目录文件夹 (用于存放我们这个页面的相关内容)。
2. study 目录内新建 images 文件夹，用于保存图片。
3. 新建首页文件 index.html（以后我们的网站首页统一规定为 index.html )。
4. 新建 style.css 样式文件。我们本次采用外链样式表。
5. 将样式引入到我们的 HTML 页面文件中。
6. 样式表写入清除内外边距的样式，来检测样式表是否引入成功。



## 3  CSS 属性书写顺序(重点)



建议遵循以下顺序：
1. 布局定位属性：display / position / float / clear / visibility / overflow（建议 display 第一个写，毕竟关系到模式）
2. 自身属性：width / height / margin / padding / border / background
3. 文本属性：color / font / text-decoration / text-align / vertical-align / white- space / break-word
4. 其他属性（CSS3）：content / cursor / border-radius / box-shadow / text-shadow / background:linear-gradient …



> 示例：

```
.jdc {
 	display: block;
 	position: relative;
	float: left;
 	width: 100px;
 	height: 100px;
 	margin: 0 10px;
 	padding: 20px 0;
 	font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
 	color: #333;
 	background: rgba(0,0,0,.5);
 	border-radius: 10px;
}
```



## 4 页面布局分析



为了提高网页制作的效率，布局时通常有以下的布局流程：
1. 必须确定页面的版心（可视区），我们测量可得知。
2. 分析页面中的行模块，以及每个行模块中的列模块。其实页面布局，就是一行行罗列而成的。
3. 制作 HTML 结构。我们还是遵循，先有结构，后有样式的原则。结构永远最重要。
4. 开始运用盒子模型的原理，通过 DIV+CSS 布局来控制网页的各个模块。



## 5 确定版心



这个页面的版心是 1200 像素，每个版心都要水平居中对齐，可以定义版心为公共类：

```
.w {
 	width: 1200px;
 	margin: auto;
}
```



## 6 头部制作



![image-20241009153749816](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009153749816.png)

- 1 号是版心盒子 header 1200 * 42 的盒子水平居中对齐，上下给一个 margin 值就可以
- 版心盒子里面包含 2 号盒子 logo
- 版心盒子里面包含 3 号盒子 nav 导航栏
- 版心盒子里面包含 4 号盒子 search 搜索框
- 版心盒子里面包含 5 号盒子 user 个人信息
- 注意：要求里面的 4 个盒子必须都是浮动



## 7 banner制作



![image-20241009153853287](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009153853287.png)

- 1 号盒子是通栏的大盒子 banner，不给宽度，给高度，给一个蓝色背景
- 2 号盒子是版心，要水平居中对齐
- 3 号盒子版心内，左对齐 subnav 侧导航栏
- 4 号盒子版心内，右对齐 course 课程



## 8 精品推荐小模块



![image-20241009153931477](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009153931477.png)

- 大盒子水平居中 goods 精品，注意此处有个盒子阴影
- 1 号盒子是标题 H3 左侧浮动
- 2 号盒子里面放链接左侧浮动， goods-item 距离可以控制链接的左右外边距（注意行内元素只给左右内外边距）
- 3 号盒子右浮动 mod 修改



## 9 精品推荐大模块



![image-20241009154007518](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009154007518.png)

- 1 号盒子为最大的盒子， box 版心水平居中对齐

- 2 号盒子为上面部分，box-hd -- 里面左侧标题 H3 左浮动，右侧链接 a 右浮动

- 3 号盒子为底下部分，box-bd -- 里面是无序列表，有 10 个小 li 组成

- 小 li 外边距的问题，这里有个小技巧：给 box-hd 宽度为 1215 就可以一行装开 5 个 li

	

复习点：我们用到清除浮动，因为 box-hd 里面的盒子个数不一定是多少，所以我们就不给高度了，但是里面的盒子浮动会影响下面的布局，因此需要清除浮动。



## 10 底部模块



![image-20241009154111959](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241009154111959.png)

- 1 号盒子是通栏大盒子，底部 footer 给高度，底色是白色
- 2 号盒子版心水平居中
- 3 号盒子版权 copyright 左对齐
- 4 号盒子链接组 links 右对齐



# 22. 定位



## 22.1 为什么需要定位



提问： 以下情况使用标准流或者浮动能实现吗？

<font color='red'>1. 某个元素可以自由的在一个盒子内移动位置，并且压住其他盒子.</font>

<font color='red'>2. 当我们滚动窗口的时候，盒子是固定屏幕某个位置的。</font>



以上效果，标准流或浮动都无法快速实现，此时<font color='red'>需要定位来实现</font>。

所以：

1. 浮动可以让多个块级盒子一行没有缝隙排列显示， 经常用于横向排列盒子。
2. 定位则是可以让盒子自由的在某个盒子内移动位置或者固定屏幕中某个位置，并且可以压住其他盒子。



## 22.2 定位组成



<font color='red'>**定位**</font>：将盒子<font color='red'>定</font>在某一个<font color='red'>位</font>置，所以<font color='red'>**定位也是在摆放盒子， 按照定位的方式移动盒子**</font>。

定位 = 定位模式 + 边偏移 。

<font color='red'>定位模式</font>用于指定一个元素在文档中的定位方式。<font color='red'>边偏移</font>则决定了该元素的最终位置。



### 1. 定位模式



> 定位模式决定元素的定位方式 ，它通过 CSS 的 <font color='red'>position</font> 属性来设置，其值可以分为四个：

| 值       | 语义         |
| -------- | ------------ |
| static   | **静态**定位 |
| relative | **相对**定位 |
| absolute | **绝对**定位 |
| fixed    | **固定**定位 |



### 2. 边偏移



> 边偏移就是定位的盒子移动到最终位置。有 <font color='red'>top、bottom、left</font> 和 <font color='red'>right</font> 4 个属性。

| 边偏移属性 | 示例          | 描述                                                   |
| ---------- | ------------- | ------------------------------------------------------ |
| top        | top: 80px;    | **顶端**偏移量，定义元素相对于其父元素**上边线的距离** |
| bottom     | bottom: 80px; | **底部**偏移量，定义元素相对于其父元素**下边线的距离** |
| left       | left: 80px;   | **左侧**偏移量，定义元素相对于其父元素**左边线的距离** |
| right      | right: 80px;  | **右侧**偏移量，定义元素相对于其父元素**右边线的距离** |



## 22.3 静态定位 static（了解）



静态定位是元素的<font color='red'>默认定位方式</font>，<font color='red'>无定位的意思</font>。

> 语法：

```
选择器 { position: static; }
```

- 静态定位按照标准流特性摆放位置，它没有边偏移
- 静态定位在布局时很少用到



## 22.4 相对定位 relative（重要）



<font color='red'>**相对定位**</font>是元素在移动位置的时候，是相对于它<font color='red'>原来的位置</font>来说的（自恋型）。

> 语法：

```
选择器 { position: relative; }
```



相对定位的特点：（务必记住）

1. 它是相对于自己原来的位置来移动的（移动位置的时候参照点是自己原来的位置）。

2. <font color='red'>原来</font>在标准流的<font color='red'>位置</font>继续占有，后面的盒子仍然以标准流的方式对待它。

  因此，相对定位并没有脱标。它最典型的应用是给绝对定位当爹的。。。



## 22.5 绝对定位 absolute（重要）



<font color='red'>**绝对定位**</font>是元素在移动位置的时候，是相对于它<font color='red'>祖先元素</font>来说的（拼爹型）。

> 语法：

```
选择器 { position: absolute; }
```



绝对定位的特点：（务必记住）

1. 如果<font color='red'>没有祖先元素</font>或者<font color='red'>祖先元素没有定位</font>，则以浏览器为准定位（Document 文档）。

2. 如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动位置。

3. 绝对定位<font color='red'>不再占有原先的位置</font>。（脱标）

  所以绝对定位是脱离标准流的。



## 22.6 子绝父相的由来



弄清楚这个口诀，就明白了绝对定位和相对定位的使用场景。

这个“子绝父相”太重要了，是我们学习定位的口诀，是定位中最常用的一种方式这句话的意思是：<font color='red'>子级是绝对定位的话，父级要用相对定位</font>。

1. 子级绝对定位，不会占有位置，可以放到父盒子里面的任何一个地方，不会影响其他的兄弟盒子。
2. 父盒子需要加定位限制子盒子在父盒子内显示。
3. 父盒子布局时，需要占有位置，因此父亲只能是相对定位。

这就是子绝父相的由来，所以<font color='red'>相对定位经常用来作为绝对定位的父级</font>。

总结：<font color='red'> 因为父级需要占有位置，因此是相对定位， 子盒子不需要占有位置，则是绝对定位</font>

当然，子绝父相不是永远不变的，如果父元素不需要占有位置，<font color='red'>子绝父绝</font>也会遇到。



## 22.7  固定定位 fixed （重要）



固定定位是元素固定于浏览器可视区的位置。主要使用场景： 可以在浏览器页面滚动时元素的位置不会改变。

> 语法：

```
选择器 { position: fixed; }
```



固定定位的特点：（务必记住）

1. 以浏览器的可视窗口为参照点移动元素。

  - <font color='red'>跟父元素没有任何关系</font>
  - 不随滚动条滚动。

2. 固定定位<font color='red'>不再占有原先的位置</font>。

  

固定定位也是脱标的，其实固定定位也可以看做是一种特殊的绝对定位。



<font color='red'>**固定定位小技巧： 固定在版心右侧位置**</font>



小算法：

1. 让固定定位的盒子 left: 50%. 走到浏览器可视区（也可以看做版心） 的一半位置。

2. 让固定定位的盒子 margin-left: 版心宽度的一半距离。 

  多走版心宽度的一半位置，就可以让固定定位的盒子贴着版心右侧对齐了。



## 22.8  粘性定位 sticky（了解）



<font color='red'>**粘性定位**</font>可以被认为是相对定位和固定定位的混合。 Sticky 粘性的

> 语法：

```
选择器 { position: sticky; top: 10px; }
```



粘性定位的特点：

1. 以浏览器的可视窗口为参照点移动元素（固定定位特点）

2. 粘性定位<font color='red'>占有原先的位置</font>（相对定位特点）

3. 必须添加 top 、left、right、bottom 其中一个才有效

  

跟页面滚动搭配使用。 兼容性较差，IE 不支持。



## 22.9 定位的总结



|                  定位模式                  |                 是否脱标                  |                  移动位置                   |           是否常用            |
| :----------------------------------------: | :---------------------------------------: | :-----------------------------------------: | :---------------------------: |
|              static 静态定位               |                    否                     |               不能使用边偏移                |             很少              |
| <font color='red'>relative 相对定位</font> |  <font color='red'>否 (占有位置)</font>   | <font color='red'>相对于自身位置移动</font> | <font color='red'>常用</font> |
| <font color='red'>absolute 绝对定位</font> | <font color='red'>是（不占有位置）</font> |  <font color='red'>带有定位的父级 </font>   | <font color='red'>常用</font> |
|  <font color='red'>fixed 固定定位</font>   | <font color='red'>是（不占有位置）</font> |   <font color='red'>浏览器可视区 </font>    | <font color='red'>常用</font> |
|              sticky 粘性定位               |               否 (占有位置)               |                浏览器可视区                 |          当前阶段少           |

1. 一定记住 相对定位、固定定位、绝对定位 两个大的特点： 1. 是否占有位置（脱标否） 2. 以谁为基准点移动位置。
2. 学习定位重点学会子绝父相。



## 22.10  定位叠放次序 z-index



在使用定位布局时，可能会出现盒子重叠的情况。此时，可以使用 <font color='red'>z-index</font> 来控制盒子的前后次序 (z轴）

> 语法：

```
选择器 { z-index: 1; }
```

- 数值可以是正整数、负整数或 0, 默认是 auto，数值越大，盒子越靠上
- 如果属性值相同，则按照书写顺序，后来居上
- 数字后面不能加单位
- 只有定位的盒子才有 z-index 属性



## 22.11 定位的拓展



### 1.绝对定位的盒子居中



加了绝对定位的盒子不能通过 <font color='red'>margin:0 auto </font>水平居中，但是可以通过以下计算方法实现水平和垂直居中。

① left: 50%;：让盒子的左侧移动到父级元素的水平中心位置。

② margin-left: -100px;：让盒子向左移动自身宽度的一半。



### 2.定位特殊特性



绝对定位和固定定位也和浮动类似。
1. 行内元素添加绝对或者固定定位，可以直接设置高度和宽度。
2. 块级元素添加绝对或者固定定位，如果不给宽度或者高度，默认大小是内容的大小。



### 3.脱标的盒子不会触发外边距塌陷



浮动元素、绝对定位(固定定位）元素的都不会触发外边距合并的问题。



### 4.绝对定位（固定定位）会完全压住盒子



浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字（图片）

但是绝对定位（固定定位） 会压住下面标准流所有的内容。

浮动之所以不会压住文字，因为浮动产生的目的最初是为了做文字环绕效果的。 文字会围绕浮动元素

![image-20241014194106761](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241014194106761.png)



# <font color='red'>网页布局总结</font>



通过盒子模型，清楚知道大部分html标签是一个盒子。

通过CSS浮动、定位 可以让每个盒子排列成为网页。

一个完整的网页，是标准流、浮动、定位一起完成布局的，每个都有自己的专门用法。



1. 标准流

  可以让盒子上下排列或者左右排列，<font color='red'>垂直的块级盒子显示就用标准流布局</font>。

2. 浮动

  可以让多个块级元素一行显示或者左右对齐盒子，<font color='red'>多个块级盒子水平显示就用浮动布局</font>。

3. 定位

  定位最大的特点是有层叠的概念，就是可以让多个盒子前后叠压来显示。<font color='red'>如果元素自由在某个盒子内移动就用定位布局</font>。



# 23.元素的显示与隐藏



类似网站广告，当我们点击关闭就不见了，但是我们重新刷新页面，会重新出现！

本质：<font color='red'>让一个元素在页面中隐藏或者显示出来</font>。

1. display 显示隐藏
2. visibility 显示隐藏
3. overflow 溢出显示隐藏



## 23.1 display 属性



display 属性用于设置一个元素应如何显示。

- display: none ；隐藏对象
- display：block ；除了转换为块级元素之外，同时还有显示元素的意思

<font color='red'>display 隐藏元素后，不再占有原来的位置。</font>

后面应用及其广泛，搭配 JS 可以做很多的网页特效。



## 23.2 visibility 可见性



<font color='red'>visibility </font>属性用于指定一个元素应可见还是隐藏。

-  visibility：visible ; 元素可视
- visibility：hidden; 元素隐藏

<font color='red'>visibility 隐藏元素后，继续占有原来的位置。</font>

如果隐藏元素想要原来位置， 就用 visibility：hidden

如果隐藏元素不想要原来位置， 就用 display：none (用处更多 重点）



## 23.3 overflow 溢出



<font color='red'>overflow</font> 属性指定了如果内容溢出一个元素的框（超过其指定高度及宽度） 时，会发生什么。

| 属性值  | 描述                                     |
| ------- | ---------------------------------------- |
| visible | 不剪切内容也不添加滚动条                 |
| hidden  | 不显示超过对象尺寸的内容，超出的部分隐藏 |
| scroll  | 不管超出内容与否，总是显示滚动条         |
| auto    | 超出自动显示滚动条，不超出不显示滚动条   |

一般情况下，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。

但是如果有定位的盒子， 请慎用overflow:hidden 因为它会隐藏多余的部分。



## 23.4 元素的显示与隐藏



类似网站广告，当我们点击关闭就不见了，但是我们重新刷新页面，会重新出现！

本质：<font color='red'>让一个元素在页面中隐藏或者显示出来</font>。



1. display 显示隐藏元素 但是不保留位置
2. visibility 显示隐藏元素 但是保留原来的位置
3. overflow 溢出显示隐藏 但是只是对于溢出的部分处理



# 24.精灵图



## 24.1 为什么需要精灵图



![image-20241014201111908](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241014201111908.png)



一个网页中往往会应用很多小的背景图像作为修饰，当网页中的图像过多时，服务器就会频繁地接收和发送请求图片，造成服务器请求压力过大，这将大大降低页面的加载速度。

因此，<font color='red'>**为了有效地减少服务器接收和发送请求的次数，提高页面的加载速度，**</font>出现了<font color='red'> CSS 精灵技术</font>（也称CSS Sprites、CSS 雪碧）。



> <font color='red'>核心原理：将网页中的一些小背景图像整合到一张大图中 ，这样服务器只需要一次请求就可以了。</font>



> <font color='red'>**精灵技术目的：**</font>
>
> <font color='red'>**为了有效地减少服务器接收和发送请求的次数，提高页面的加载速度**</font>

![image-20241014201501121](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241014201501121.png)



## 24.2 精灵图（sprites）的使用



> 使用精灵图核心：

1. 精灵技术主要针对于背景图片使用。就是把多个小背景图片整合到一张大图片中。
2. 这个大图片也称为 sprites 精灵图 或者 雪碧图
3. 移动背景图片位置， 此时可以使用 <font color='red'>background-position</font> 。
4. 移动的距离就是这个目标图片的<font color='red'> x </font>和 <font color='red'>y</font> 坐标。注意网页中的坐标有所不同
5. 因为一般情况下都是往上往左移动，所以数值是负值。
6. 使用精灵图的时候需要精确测量，每个小背景图片的大小和位置。



> 使用精灵图核心总结：

1. 精灵图主要针对于小的背景图片使用。
2. 主要借助于背景位置来实现---<font color='red'>background-position</font> 。
3. 一般情况下精灵图都是负值。（千万注意网页中的坐标： x轴右边走是正值，左边走是负值， y轴同理。）



# 25.字体图标



## 25.1 字体图标的产生



字体图标使用场景： 主要用于显示网页中通用、常用的一些小图标。

精灵图是有诸多优点的，但是缺点很明显。
1. 图片文件还是比较大的。
2. 图片本身放大和缩小会失真。
3. 一旦图片制作完毕想要更换非常复杂。

此时，有一种技术的出现很好的解决了以上问题，就是<font color='red'>字体图标 iconfont</font>。

<font color='red'>字体图标</font>可以为前端工程师提供一种方便高效的图标使用方式，<font color='red'>展示的是图标，本质属于字体</font>。



## 25.2 字体图标的优点



- 轻量级：一个图标字体要比一系列的图像要小。一旦字体加载了，图标就会马上渲染出来，减少了服务器请求
- 灵活性：本质其实是文字，可以很随意的改变颜色、产生阴影、透明效果、旋转等
- 兼容性：几乎支持所有的浏览器，请放心使用

注意： 字体图标不能替代精灵技术，只是对工作中图标部分技术的提升和优化。

**总结：**

1. 如果遇到一些结构和样式比较简单的小图标，就用字体图标。

	![image-20241016215335951](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016215335951.png)

2. 如果遇到一些结构和样式复杂一点的小图片，就用精灵图。

![image-20241016215343646](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016215343646.png)

## 25.3 字体图标的下载



推荐下载网站：

- <font color='red'>**icomoon 字库** http://icomoon.io </font>推荐指数 ★★★★★

	IcoMoon 成立于 2011 年，推出了第一个自定义图标字体生成器，它允许用户选择所需要的图标，使它们成一字型。该字库内容种类繁多，非常全面，唯一的遗憾是国外服务器，打开网速较慢。

	

- <font color='red'>**阿里 iconfont 字库** http://www.iconfont.cn/ </font>推荐指数 ★★★★★

	这个是阿里妈妈 M2UX 的一个 iconfont 字体图标字库，包含了淘宝图标库和阿里妈妈图标库。可以使用 AI制作图标上传生成。 重点是，免费！



## 25.4 字体图标的引入



<font color='red'>下载完毕之后，注意原先的文件不要删，后面会用。</font>



1. 把下载包里面的 fonts 文件夹放入页面根目录下

![image-20241016215731766](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016215731766.png)



> 字体文件格式
>
> 不同浏览器所支持的字体格式是不一样的，字体图标之所以兼容，就是因为包含了主流浏览器支持的字体文件。
> 1. TureType(<font color='red'>.ttf</font>)格式.ttf字体是Windows和Mac的最常见的字体，支持这种字体的浏览器有IE9+、Firefox3.5+、
> Chrome4+、Safari3+、Opera10+、iOS Mobile、Safari4.2+；
> 2. Web Open Font Format(<font color='red'>.woff</font>)格式woff字体，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome6+、
> Safari3.6+、Opera11.1+；
> 3. Embedded Open Type(<font color='red'>.eot</font>)格式.eot字体是IE专用字体，支持这种字体的浏览器有IE4+；
> 4. SVG(<font color='red'>.svg</font>)格式.svg字体是基于SVG字体渲染的一种格式，支持这种字体的浏览器有Chrome4+、Safari3.1+、
> Opera10.0+、iOS Mobile Safari3.2+；



2. 在 CSS 样式中全局声明字体： 简单理解把这些字体文件通过css引入到我们页面中。

```
@font-face {
 	font-family: 'icomoon';
 	src: url('fonts/icomoon.eot?7kkyc2');
 	src: url('fonts/icomoon.eot?7kkyc2#iefix') format('embedded-opentype'),
 		url('fonts/icomoon.ttf?7kkyc2') format('truetype'),
 		url('fonts/icomoon.woff?7kkyc2') format('woff'),
 		url('fonts/icomoon.svg?7kkyc2#icomoon') format('svg');
 	font-weight: normal;
 	font-style: normal;
}
```



3. html 标签内添加小图标。

![image-20241016215952240](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016215952240.png)

```
<span> </span> 
```



4. 给标签定义字体。

```
span {
 font-family: "icomoon";
}
```

务必保证 这个字体和上面@font-face里面的字体保持一致

![image-20241016220046090](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016220046090.png)

## 25.5 字体图标的追加



如果工作中，原来的字体图标不够用了，我们需要添加新的字体图标到原来的字体文件中。

把压缩包里面的 selection.json 从新上传，然后选中自己想要新的图标，从新下载压缩包，并替换原来的文件即可。

![image-20241016220121406](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016220121406.png)

**字体图标加载的原理：**

![image-20241016220139236](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016220139236.png)

# 26. CSS 三角



网页中常见一些三角形，使用 CSS 直接画出来就可以，不必做成图片或者字体图标。

一张图， 你就知道 CSS 三角是怎么来的了, 做法如下：

![image-20241016220220352](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016220220352.png)

```
div {
 	width: 0;
 	height: 0;
 	line-height: 0;
 	font-size: 0;
	border: 50px solid transparent;
 	border-left-color: pink;
}
```

其中transparent为透明的意思。实现效果：![image-20241023195036543](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023195036543.png)



# 27. CSS 用户界面样式



## 27.1 什么是界面样式



所谓的<font color='red'>界面样式</font>，就是更改一些用户操作样式，以便提高更好的用户体验。

- 更改用户的鼠标样式
- 表单轮廓
- 防止表单域拖拽



## 27.2 鼠标样式 cursor



```
li {cursor: pointer; }
```

设置或检索在对象上移动的鼠标指针采用何种系统预定义的光标形状。

| 属性值      | 描述      |
| ----------- | --------- |
| default     | 小白 默认 |
| pointer     | 小手      |
| move        | 移动      |
| text        | 文本      |
| not-allowed | 禁止      |



## 27.3 轮廓线 outline



给表单（input类型）添加 outline: 0; 或者 outline: none; 样式之后，就可以去掉默认的蓝色边框。

```
input {outline: none; }
```



## 27.4 防止拖拽文本域 resize



实际开发中，我们文本域右下角是不可以拖拽的。

```
textarea{ resize: none;}
```



# 28. vertical-align 属性应用



CSS 的<font color='red'> vertical-align </font>属性使用场景： 经常用于设置图片或者表单(行内块元素）和文字垂直对齐。

官方解释： 用于设置一个元素的<font color='red'>垂直对齐方式</font>，但是它只针对于行内元素或者行内块元素有效。



> 语法：

```
vertical-align : baseline | top | middle | bottom 
```



|    值    |                 描述                 |
| :------: | :----------------------------------: |
| baseline |    默认。元素放置在父元素的基线上    |
|   top    | 把元素的顶端与行中最高元素的顶端对齐 |
|  middle  |      把此元素放置在父元素的中部      |
|  bottom  | 把元素的顶端与行中最低元素的顶端对齐 |



![image-20241016221013102](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016221013102.png)



## 28.1 图片、表单和文字对齐



图片、表单都属于行内块元素，默认的 vertical-align 是基线对齐。

![image-20241016221134768](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016221134768.png)



此时可以给图片、表单这些行内块元素的<font color='red'> vertical-align 属性设置为 middle</font> 就可以让文字和图片垂直居中对齐了。



## 28.2 解决图片底部默认空白缝隙问题



bug：图片底侧会有一个空白缝隙，原因是行内块元素会和文字的基线对齐。

主要解决方法有两种：

1. 给图片添加<font color='red'> vertical-align:middle | top| bottom</font> 等。 （提倡使用的）
2. 把图片转换为块级元素 <font color='red'>display: block;</font>

![image-20241016221242647](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241016221242647.png)



# 29. 溢出的文字省略号显示



## 29.1 单行文本溢出显示省略号



![image-20241023192808893](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023192808893.png)

```
/*1. 先强制一行内显示文本*/
 white-space: nowrap; （ 默认 normal 自动换行）
 /*2. 超出的部分隐藏*/
 overflow: hidden;
 /*3. 文字用省略号替代超出的部分*/
 text-overflow: ellipsis;
```

文字强制一行内显示：white-space : nowrap ;



## 29.2 多行文本溢出显示省略号



![image-20241023192827243](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023192827243.png)



多行文本溢出显示省略号，有较大兼容性问题， 适合于webKit浏览器或移动端（移动端大部分是webkit内核）

```
overflow: hidden;
text-overflow: ellipsis;
/* 弹性伸缩盒子模型显示 */
display: -webkit-box;
/* 限制在一个块元素显示的文本的行数 */
-webkit-line-clamp: 2;
/* 设置或检索伸缩盒对象的子元素的排列方式 */
-webkit-box-orient: vertical;
```

​	<font color='red'>更推荐让后台人员来做这个效果，因为后台人员可以设置显示多少个字，操作更简单</font>



# 30.常见布局技巧



> **巧妙利用一个技术更快更好的布局：**
>
> 1.margin负值的运用
> 2.文字围绕浮动元素
> 3.行内块的巧妙运用
> 4.CSS三角强化



## 30.1  margin负值运用



> 相邻盒子边框加浮动合并后变粗的问题

![image-20241023193416412](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023193416412.png)

![image-20241023193432560](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023193432560.png)

1. 让每个盒子margin 往左侧移动 -1px 正好压住相邻盒子边框
2. 鼠标经过某个盒子的时候，提高当前盒子的层级即可（如果没有有定位，则加相对定位（保留位置），如
	果有定位，则加z-index）



## 30.2 文字围绕浮动元素



![image-20241023193643182](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023193643182.png)

![image-20241023193855630](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023193855630.png)

> 浮动最开始就是为了实现文字的环绕效果的

若做一个大盒子，左边小盒子，右边文字的布局，只给左边盒子加浮动即可使文字环绕左盒子显示，巧妙运用浮动元素不会压住文字的特性。



## 30.3 行内块巧妙运用



![image-20241023194317676](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023194317676.png)

页码在页面中间显示:
1. 把这些链接盒子转换为行内块， 之后给父级指定 text-align:center;
2. 利用行内块元素中间有缝隙实现页码间有一定距离的效果，并且给父级添加 text-align:center; 行内块元素会水平会居中



##  30.4 CSS 三角强化



![image-20241023194427987](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241023194427987.png)



> 代码：

```
width: 0;
height: 0;
border-color: transparent red transparent transparent;
border-style: solid;
border-width: 22px 8px 0 0;
             /*上   右  下 左*/
```



# 31. CSS初始化



不同浏览器对有些标签的默认值是不同的，为了消除不同浏览器对HTML文本呈现的差异，照顾浏览器的兼容，我们需要对CSS 初始化

简单理解： CSS初始化是指重设浏览器的样式。 (也称为CSS reset）

每个网页都必须首先进行 CSS初始化。

这里我们以 京东CSS初始化代码为例。（CSS初始化代码详情见 桌面\前端项目\案例\京东CSS初始化）



**Unicode编码字体：**

把中文字体的名称用相应的Unicode编码来代替，这样就可以有效的避免浏览器解释CSS代码时候出现乱码的问题。

> 比如：

黑体 \9ED1\4F53

宋体 \5B8B\4F53

微软雅黑 \5FAE\8F6F\96C5\9ED1

其中一组为一个汉字



------



# <font color='red'>HTML5和CSS3提高</font>



# 32.HTML5的新特性



<font color='red'>HTML5</font> 的新增特性主要是针对于以前的不足，增加了一些<font color='red'>新的标签</font>、<font color='red'>新的表单</font>和<font color='red'>新的表单属性</font>等。

这些新特性都有兼容性问题，基本是 IE9+ 以上版本的浏览器才支持，如果不考虑兼容性问题，可以大量使用这些新特性。

声明：

1. 新特性增加了很多，但是我们专注于开发常用的新特性。
2. 基础班我们讲解部分新特性，到了就业班还会继续讲解其他新特性。



## 32.1 HTML5 新增的语义化标签



> 以前布局，我们基本用 div 来做。div 对于搜索引擎来说，是没有语义的。

```
<div class=“header”> </div>
<div class=“nav”> </div>
<div class=“content”> </div>
<div class=“footer”> </div>
```



------

**新增标签**

- `<header>`：头部标签
- `<nav>`：导航标签
- `<article>`：内容标签
- `<section>`：定义文档某个区域
- `<aside>`：侧边栏标签
- `<footer>`：尾部标签

![image-20241030220927056](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241030220927056.png)

<font color='red'>**注意：**</font>

- 这种语义化标准主要是针对<font color='red'>搜索引擎</font>的
- 这些新标签页面中可以使用<font color='red'>多次</font>
- 在 IE9 中，需要把这些元素转换为<font color='red'>块级元素</font>
- 其实，我们移动端更喜欢使用这些标签
- HTML5 还增加了很多其他标签，我们后面再慢慢学



## 32.2 HTML5 新增的多媒体标签



新增的多媒体标签主要包含两个：

1. <font color='red'>音频：`<audio>` </font>
2. <font color='red'>视频：``<video>``</font>

使用它们可以很方便的在页面中嵌入音频和视频，而不再去使用 flash 和其他浏览器插件。



HTML5 在不使用插件的情况下，也可以原生的支持视频格式文件的播放，当然，支持的格式是有限的。



### 1. 视频``<video>``



当前 `<video>` 元素支持三种视频格式： 尽量使用 mp4格式



| 浏览器\|是否支持  | MP4                                                          | WebM | Ogg  |
| ----------------- | ------------------------------------------------------------ | ---- | ---- |
| Internet Explorer | 是                                                           | 否   | 否   |
| Chrome            | 是                                                           | 是   | 是   |
| Firefox           | 是<br />从Firefox 21版本开始；Linux系统从 Firefox 30 版本开始 | 是   | 是   |
| Safari            | 是                                                           | 否   | 否   |
| Opera             | 是<br />从 Opera 25 版本开始                                 | 是   | 是   |



> 语法：

```
<video src="文件地址" controls="controls"></video>
```

```
 <video controls="controls" width="300">
 <source src="move.ogg" type="video/ogg" >
 <source src="move.mp4" type="video/mp4" >
 您的浏览器暂不支持 <video> 标签播放视频
 </ video >
```



> **常见属性**



| 属性     | 值                                                 | 描述                                                         |
| -------- | -------------------------------------------------- | ------------------------------------------------------------ |
| autoplay | autoplay                                           | 视频就绪自动播放（谷歌浏览器需要添加muted来解决自动播放问题） |
| controls | controls                                           | 向用户显示播放控件                                           |
| width    | pixels（像素）                                     | 设置播放器宽度                                               |
| height   | pixels（像素）                                     | 设置播放器高度                                               |
| loop     | loop                                               | 播放完是否继续播放该视频，循环播放                           |
| preload  | auto（预先加载视频）<br />nono（不应预先加载视频） | 规定是否预加载视频（如果有了autoplay 就忽略该属性）          |
| src      | url                                                | 视频url地址                                                  |
| poster   | Imgurl                                             | 加载等待的画面图片                                           |
| muted    | muted                                              | 静音播放                                                     |



### 2.音频`<audio>`



当前 `<audio>` 元素支持三种音频格式：

| 浏览器\|是否支持  | MP3  | Wav  | Ogg  |
| ----------------- | ---- | ---- | ---- |
| Internet Explorer | 是   | 否   | 否   |
| Chrome            | 是   | 是   | 是   |
| Firefox           | 是   | 是   | 是   |
| Safari            | 是   | 是   | 否   |
| Opera             | 是   | 是   | 是   |



> 语法：



```
<audio src="文件地址" controls="controls"></audio>
```

```
< audio controls="controls" >
 <source src="happy.mp3" type="audio/mpeg" >
 <source src="happy.ogg" type="audio/ogg" >
 您的浏览器暂不支持 <audio> 标签。
 </ audio>
```



> **常见属性：**



| 属性     | 值       | 描述                                           |
| -------- | -------- | ---------------------------------------------- |
| autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放         |
| controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮 |
| loop     | loop     | 如果出现该属性，则每当音频结束时重新开始播放   |
| src      | url      | 要播放的音频的url                              |

- 谷歌浏览器把音频和视频自动播放禁止了



### 3.多媒体标签总结



- 音频标签和视频标签使用方式基本一致
- 浏览器支持情况不同
- 谷歌浏览器把音频和视频自动播放禁止了
- 我们可以给视频标签添加 muted 属性来静音播放视频，音频不可以（可以通过JavaScript解决）
- 视频标签是重点，我们经常设置自动播放，不使用 controls 控件，循环和设置大小属性



## 32.3 HTML5 新增的 input 类型



| 属性值            | 说明                           |
| ----------------- | ------------------------------ |
| type=“email”      | 限制用户输入必须为Email类型    |
| type=“url”        | 限制用户输入必须为URL类型      |
| type=“date”       | 限制用户输入必须为日期类型     |
| type=“time”       | 限制用户输入必须为时间类型     |
| type=“month”      | 限制用户输入必须为月类型       |
| type=“week”       | 限制用户输入必须为周类型       |
| **type=“number”** | **限制用户输入必须为数字类型** |
| **type=“tel”**    | **手机号码**                   |
| **type=“search”** | **搜索框**                     |
| type=“color”      | 生成一个颜色选择表单           |



## 32.4 HTML5 新增的表单属性



| 属性         | 值        | 说明                                                         |
| ------------ | --------- | ------------------------------------------------------------ |
| required     | required  | 表单拥有该属性表示其内容不能为空，必填                       |
| placeholder  | 提示文本  | 表单的提示信息，存在默认值将不显示                           |
| autofocus    | autofocus | 自动聚焦属性，页面加载完成后自动聚焦到指定表单               |
| autocomplete | off/on    | 当用户在字段开始键入时，浏览器基于之前键入过的值，应该显示出在字段<br />中填写的选项。<br />默认已经打开，如autocomplete=“on”，关闭 autocomplete=“off”<br />需要放在表单内，同时加上name属性，同时成功提交 |
| multiple     | multiple  | 可以多选文件提交                                             |



<font color='red'>可以通过以下设置方式修改placeholder里面的字体颜色：</font>

```
input::placeholder {
 color: pink;
 }
```



# 33. CSS3的新特性



## 33.1 CSS3 的现状



- 新增的CSS3特性有兼容性问题，ie9+才支持
- 移动端支持优于 PC 端
- 不断改进中
- 应用相对广泛
- 现阶段主要学习：<font color='red'>新增选择器</font>和<font color='red'>盒子模型</font>以及<font color='red'>其他特性</font>



> **CSS3新增选择器**



CSS3 给我们新增了选择器，可以更加便捷，更加自由的选择目标元素。
1. 属性选择器
2. 结构伪类选择器
3. 伪元素选择器



## 33.2 属性选择器



属性选择器可以根据<font color='red'>元素特定属性</font>的来选择元素。 这样就可以不用借助于类或者id选择器。



| 选择符        | 简介                                        |
| ------------- | ------------------------------------------- |
| E[att]        | 选择具有 att 属性的 E 元素                  |
| E[att=“val”]  | 选择具有 att 属性且属性值等于 val 的 E 元素 |
| E[att^=“val”] | 匹配具有 att 属性且值以 val 开头的 E 元素   |
| E[att$=“val”] | 匹配具有 att 属性且值以 val 结尾的 E 元素   |
| E[att*=“val”] | 匹配具有 att 属性且值中含有 val 的 E 元素   |



<font color='red'>**注意：类选择器、属性选择器、伪类选择器，权重为 10**</font>



## 33.3 结构伪类选择器



结构伪类选择器主要根据<font color='red'>文档结构</font>来选择器元素， 常用于根据父级选择器里面的子元素



| 选择符           | 简介                          |
| ---------------- | ----------------------------- |
| E:first-child    | 匹配父元素中的第一个子元素 E  |
| E:last-child     | 匹配父元素中最后一个 E 元素   |
| E:nth-child(n)   | 匹配父元素中的第 n 个子元素 E |
| E:first-of-type  | 指定类型 E 的第一个           |
| E:last-of-type   | 指定类型 E 的最后一个         |
| E:nth-of-type(n) | 指定类型 E 的第 n 个          |



<font color='red'>**注意：类选择器、属性选择器、伪类选择器，权重为 10**</font>



------



### **1. nth-child（n）** 选择某个父元素的一个或多个特定的子元素（重点）



- <font color='red'>n 可以是数字，关键字和公式</font>
- n 如果是数字，就是选择第 n 个子元素， 里面数字从1开始…
- n 可以是关键字：even 偶数，odd 奇数
- n 可以是公式：常见的公式如下 ( 如果n是公式，则从0开始计算，但是第 0 个元素或者超出了元素的个数会被忽略 )

| 公示 | 取值                           |
| ---- | ------------------------------ |
| 2n   | 偶数                           |
| 2n+1 | 奇数                           |
| 5n   | 5   10   15…                   |
| n+5  | 从第5个开始（包含第5个）到最后 |
| -n+5 | 前5个（包含第5个）…            |



------



### 2. nth-child 和 nth-of-type 的区别



1. <font color='red'>nth-child 对父元素里面所有孩子排序选择（序号是固定的） 先找到第n个孩子，然后看看是否和E匹配</font>
2. <font color='red'>nth-of-type 对父元素里面指定子元素进行排序选择。 先去匹配E ，然后再根据E 找第n个孩子</font>



例如：

```
<style>
	/*执行的时候先看:nth-child，先把第一个孩子选出来，再看能不能和前面的div匹配上。
	匹配不上，故没有变红的标签。*/
	section div:nth-child(1){
		background-color:red;
	}
	/*执行的时候首先看前面的条件，选出是div的盒子，然后再看:nth-of-type是第几个孩子。
	所以熊大这个标签变红*/
	section div:nth-of-type(1){
		background-color:red;
	}
<style>

<section>
	<p>光头强<p>
	<div>熊大<div>
	<div>熊二<div>
<section>
```



------



### 3. 小结

- 结构伪类选择器一般用于选择父级里面的第几个孩子
- nth-child 对父元素里面所有孩子排序选择（序号是固定的） 先找到第n个孩子，然后看看是否和E匹配
- nth-of-type 对父元素里面指定子元素进行排序选择。 先去匹配E ，然后再根据E 找第n个孩子
- 关于 nth-child（n） 我们要知道 n 是从 0 开始计算的，要记住常用的公式
- 如果是无序列表，我们肯定用 nth-child 更多
- 类选择器、属性选择器、伪类选择器，权重为 10。



## 33.4 伪元素选择器（重点）



伪元素选择器可以帮助我们利用CSS创建新标签元素，而不需要HTML标签，从而简化HTML结构。



| 选择符   | 简介                     |
| -------- | ------------------------ |
| ::before | 在元素内部的前面插入内容 |
| ::after  | 在元素内部的后面插入内容 |

**<font color='red'>注意：</font>**

- <font color='red'>before</font> 和 <font color='red'>after</font>创建一个元素，但是属于行内元素
- 新创建的这个元素在文档树中是找不到的，所以我们称为<font color='red'>伪元素</font>
- <font color='red'>语法： element::before {} </font>
- before 和 after 必须有 <font color='red'>content 属性</font>
- before 在父元素内容的前面创建元素，after 在父元素内容的后面插入元素
- <font color='red'>伪元素选择器</font>和<font color='red'>标签选择器</font>一样，权重为 1



### 伪元素选择器使用场景



#### 1. 伪元素字体图标



![image-20241031205417400](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031205417400.png)

```
p::before {
 	position: absolute;
 	right: 20px;
 	top: 10px;
	content: '\e91e';
 	font-size: 20px;
 }
```



#### 2. 仿土豆效果



![image-20241031205622052](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031205622052.png)

```
/* 当我们鼠标经过了 土豆这个盒子，就让里面before遮罩层显示出来 
:hover前的是鼠标经过的元素，:hover后的是要变化的元素*/
.tudou:hover::before {
 /* 而是显示元素 */
 display: block;
}
```



#### 3. 伪元素清除浮动



> 1. 额外标签法也称为隔墙法，是 W3C 推荐的做法。
> 2. 父级添加 overflow 属性
> 3. 父级添加after伪元素
> 4. 父级添加双伪元素



**额外标签法**也称为隔墙法，是 W3C 推荐的做法。![image-20241031210139804](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031210139804.png)

注意： 要求这个新的空标签必须是块级元素。

后面两种伪元素清除浮动算是第一种额外标签法的一个升级和优化

**父级添加after伪元素**

![image-20241031210354276](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031210354276.png)

**父级添加双伪元素**

![image-20241031210745764](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031210745764.png)



## 33.5 CSS3盒子模型



CSS3 中可以通过<font color='red'> box-sizing</font> 来指定盒模型，有2个值：即可指定为 <font color='red'>content-box</font>、<font color='red'>border-box</font>，这样我们计算盒子大小的方式就发生了改变。



可以分成两种情况：
1. box-sizing: content-box 盒子大小为 width + padding + border （以前默认的）

2. box-sizing: border-box 盒子大小为 width

  

如果盒子模型我们改为了box-sizing: border-box ， 那padding和border就不会撑大盒子了（前提padding和border不会超过width宽度）



**一般在CSS开头*中加上box-sizing:border-box;来规定此页面盒子大小的计算方式**



## 33.6 CSS3其他特性（了解）



> 1. 图片变模糊
> 2. 计算盒子宽度 width: calc 函数



### 1.CSS3滤镜filter:



filter CSS属性将模糊或颜色偏移等图形效果应用于元素。

```
filter: 函数();    例如： filter: blur(5px); blur模糊处理 数值越大越模糊
```

![image-20241031211312080](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031211312080.png)



### 2. CSS3 calc 函数:



calc() 此CSS函数让你在声明CSS属性值时执行一些计算。

```
width: calc(100% - 80px);
```

括号里面可以使用 + - * / 来进行计算。



## 33.7 CSS3 过渡（重点）



```
transition: 要过渡的属性 花费时间 运动曲线 何时开始;
```

1. **属性** ： 想要变化的 css 属性， 宽度高度 背景颜色 内外边距都可以 。如果想要所有的属性都变化过渡， 写一个all 就可以。
2. **花费时间**： 单位是 秒（必须写单位） 比如 0.5s 
3. **运动曲线**： 默认是 ease （可以省略）
4. **何时开始** ：单位是 秒（必须写单位）可以设置延迟触发时间 默认是 0s （可以省略）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031222954581.png" alt="image-20241031222954581" style="zoom: 50%;" />

| 运动曲线名称 | 效果         |
| ------------ | ------------ |
| linear       | 匀速         |
| ease         | 逐渐慢下来   |
| ease-in      | 加速         |
| ease-out     | 减速         |
| ease-in-out  | 先加速后减速 |

**<font color='red'>记住过渡的使用口诀： 谁做过渡给谁加</font>**



# 34. 广义的H5



## 狭义的HTML5 CSS3



![image-20241031223305741](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031223305741.png)

## 广义的HTML5



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241031223342213.png" alt="image-20241031223342213" style="zoom:33%;" />



1. 广义的 HTML5 是 HTML5 本身 + CSS3 + JavaScript 。
2. 这个集合有时称为 HTML5 和朋友，通常缩写为 HTML5 。
3. 虽然 HTML5 的一些特性仍然不被某些浏览器支持，但是它是一种发展趋势



------



# <font color='red'>PC端品优购项目</font>



## 1. 品优购项目规划



### 1.1 网站制作流程



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224200318551.png" alt="image-20241224200318551" style="zoom: 50%;" />

> 网页美工会制作原型图和psd效果图



现阶段，我们主要做前台页面设计



### 1.2 品优购项目整体介绍



- 项目名称：品优购
- 项目描述：品优购是一个电商网站，我们要完成 PC 端首页、列表页、注册页面的制作

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224200426494.png" alt="image-20241224200426494" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224200441481.png" alt="image-20241224200441481" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224200451756.png" alt="image-20241224200451756" style="zoom:50%;" />



### 1.3 品优购项目的学习目的



1. 电商类网站比较综合，里面需要大量的布局技术，包括布局方式、常见效果以及周边技术。
2. 品优购项目能复习、总结、提高基础班所学布局技术。
3. 写完品优购项目，能对实际开发中<font color='red'>**制作 PC 端页面流程**</font>有一个整体的感知。
4. 为后期学习移动端项目做铺垫。



### 1.4 开发工具以及技术栈



**1.开发工具**

​	VScode 、Photoshop（fw）、主流浏览器（以Chrome浏览器为主）

**2.技术栈**

- 利用 HTML5 + CSS3 手动布局，可以大量使用 H5 新增标签和样式
- 采取结构与样式相分离，模块化开发
- 良好的代码规范有利于团队更好的开发协作，提高代码质量，因此品优购项目里面，请同学们遵循以下代码规范。（详情见素材文件夹--- <font color='red'>品优购代码规范.md</font>）



### 1.5 品优购项目搭建工作



1. 需要创建如下文件夹：

| 名称             | 说明    |
| ---------------- | ------- |
| 项目文件夹       | shoping |
| 样式类图片文件夹 | images  |
| 样式文件夹       | css     |
| 产品类文件夹     | upload  |
| 字体类文件夹     | fonts   |
| 脚本文件夹       | js      |



2. 需要创建如下文件：

| 名称              | 说明       |
| ----------------- | ---------- |
| 首页              | index.html |
| CSS初始化样式文件 | base.css   |
| CSS公共样式文件   | common.css |



有些网站初始化的不太提倡 * { margin: 0; padding: 0; }

> 需要处理标签过多，占用浏览器资源

比如新浪：

html,body,ul,li,ol,dl,dd,dt,p,h1,h2,h3,h4,h5,h6,form,fieldset,legend,img{margin:0;padding:0}



3. 模块化开发



所谓的模块化：将一个项目按照功能划分，一个功能一个模块，互不影响模块化开发具有重复使用、更换方便等优点

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224210955199.png" alt="image-20241224210955199" style="zoom:50%;" />



- 有些样式和结构在很多页面都会出现，比如页面头部和底部，大部分页面都有。此时，可以把这些结构和样式单独作为一个模块，然后重复使用
- 这里最典型的应用就是 <font color='red'>common.css 公共样式</font>。写好一个样式，其余的页面用到这些相同的样式
- 模块化开发具有重复使用、修改方便等优点

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224211046404.png" alt="image-20241224211046404" style="zoom:33%;" />

<font color='red'>common.css</font> 公共样式里面包含<font color='red'>版心宽度</font>、<font color='red'>清除浮动</font>、<font color='red'>页面文字颜色</font>等公共样式。



### 1.6 网站 favicon 图标



<font color='red'>favicon.ico</font> 一般用于作为缩略的网站标志，它显示在浏览器的地址栏或者标签上。

目前主要的浏览器都支持<font color='red'> favicon.ico</font> 图标。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224211159307.png" alt="image-20241224211159307" style="zoom:33%;" />



#### ①制作favicon图标



1. 把品优购图标切成 png 图片。
2. 把 png 图片转换为 ico 图标，这需要借助于第三方转换网站，例如<font color='red'>比特虫：http://www.bitbug.net/</font>



#### ②favicon图标放到网站根目录下



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224211317339.png" alt="image-20241224211317339" style="zoom:33%;" />

#### ③HTML页面引入favicon图标



在html 页面里面的 `<head> </head>`元素之间引入代码。

```
<link rel="shortcut icon" href="favicon.ico" type="image/x-icon"/> 
```



### 1.7 网站TDK三大标签SEO优化



<font color='red'>SEO（Search Engine Optimization）</font>汉译为<font color='red'>搜索引擎优化</font>，是一种利用搜索引擎的规则提高网站在有关搜索引擎内自然排名的方式。

SEO 的目的是<font color='red'>对网站进行深度的优化</font>，从而帮助网站获取免费的流量，进而在搜索引擎上提升网站的排名，提高网站的知名度。

页面必须有三个标签用来符合 SEO 优化。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224211536274.png" alt="image-20241224211536274" style="zoom:33%;" />



#### ①title 网站标题



title 具有不可替代性，是我们内页的第一个重要标签，是搜索引擎了解网页的入口和对网页主题归属的最佳判断点。

建议：**<font color='red'>网站名（产品名）- 网站的介绍</font>** （尽量不要超过30个汉字）



例如：

- 京东(JD.COM)-综合网购首选-正品低价、品质保障、配送及时、轻松购物！
- 小米商城 - 小米5s、红米Note 4、小米MIX、小米笔记本官方网站



#### ②description 网站说明



<font color='red'>简要说明我们网站主要是做什么的。</font>

我们提倡，description 作为网站的总体业务和主题概括，多采用“我们是…”、“我们提供…”、“×××网作为…”、“电话：010…”之类语句。



例如：

```
<meta name="description" content="京东JD.COM-专业的综合网上购物商城,销售家电、数码通讯、电脑、
家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物
体验!" />
```



#### ③keywords 关键字



<font color='red'>keywords 是页面关键词，是搜索引擎的关注点之一。</font>

keywords 最好限制为 6～8 个关键词，关键词之间用英文逗号隔开，采用 <font color='red'>关键词1,关键词2 </font>的形式。



例如：

```
<meta name= " keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配
件,手表,存储卡,京东" />
```



对于我们前端人员来说，我们只需要准备好这三个标签，具体里面的内容，有专门的 SEO 人员准备。



## 2. 品优购首页制作



网站的首页一般都是使用 index 命名，比如 index.html 或者 index.php 。

我们开始制作首页的头部和底部的时候，根据模块化开发，样式要写到common.css里面



### 2.1 常用模块类名命名



| 名称             | 说明                  |
| ---------------- | --------------------- |
| 快捷导航栏       | shortcut              |
| 头部             | header                |
| 标志             | logo                  |
| 购物车           | shoper                |
| 搜索             | search                |
| 热点词           | hotwrods              |
| 导航             | nav                   |
| 导航左侧         | dropdowm 包含 .dd .tt |
| 导航右侧         | navitems              |
| 页面底部         | footer                |
| 页面底部服务模块 | mod_service           |
| 页面底部帮助模块 | mod_help              |
| 页面底部版权模块 | mod_copyright         |



### 2.2 快捷导航 shortcut 制作



![image-20241224212248733](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212248733.png)

- 通栏的盒子命名为 shortcut ，是快捷导航的意思。 注意这里的行高，可以继承给里面的子盒子
- 里面包含版心的盒子
- 版心盒子里面包含 1 号左侧盒子左浮动
- 版心盒子里面包含 2 号右侧盒子右浮动
- 需要用到字体图标



### 2.3 header 制作



![image-20241224212412701](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212412701.png)

1. header 盒子必须要有高度

2. 1 号盒子是 logo 标志定位

3. 2 号盒子是 search 搜索模块定位

4. 3 号盒子是 hotwords 热词模块定位

5. 4 号盒子是 shopcar 购物车模块

	- count 统计部分用绝对定位做
	- count 统计部分不要给宽度，因为可能买的件数比较多，让件数撑开就好了，给一个高度
	- 一定注意左下角不是圆角，其余三个是圆角 写法： border-radius: 7px 7px 7px 0;

	

**LOGO SEO 优化**



1. logo 里面首先放一个 <font color='red'>h1</font> 标签，目的是为了提权，告诉搜索引擎，这个地方很重要。
2. h1 里面再放一个<font color='red'>链接</font>，可以返回首页的，把 logo 的背景图片给链接即可。
3. 为了搜索引擎收录我们，我们链接里面要放<font color='red'>文字（网站名称）</font>，但是文字不要显示出来。
  - 方法1：<font color='red'>text-indent </font>移到盒子外面（<font color='red'>text-indent: -9999px</font>) ，然后 <font color='red'>overflow:hidden </font>，淘宝的做法。
  - 方法2：直接给 <font color='red'>font-size: 0;</font> 就看不到文字了，京东的做法。
4. 最后给链接一个<font color='red'> title</font> 属性，这样鼠标放到 logo 上就可以看到提示文字了。



2 号盒子是 search 搜索模块定位

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212740499.png" alt="image-20241224212740499" style="zoom:33%;" />



### 2.4 nav 导航制作



![image-20241224212812039](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212812039.png)



- nav 盒子通栏有高度，而且有个下边框
- 1 号盒子左侧浮动，dropdown 
- 2 号盒子左侧浮动，navitems 导航栏组
- 1号盒子有讲究，根据相关性 里面包含 .dt 和 .dd 两个盒子

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212843160.png" alt="image-20241224212843160" style="zoom: 50%;" />



### 2.5 footer 底部制作



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224212919307.png" alt="image-20241224212919307" style="zoom:50%;" />



- footer 页面底部盒子通栏给一个高度和灰色的背景
- footer 里面有一个大的版心
- 版心里面包含 1 号盒子，mod_service 是服务模块，mod 是模块的意思
- 版心里面包含 2 号盒子，mod_help 是帮助模块
- 版心里面包含 3 号盒子，mod_copyright 是版权模块



### 2.6 main 主体模块制作



以前书写的就是模块化中的公共部分。

<font color='red'>main</font> 主体模块是<font color='red'> index</font><font color='red'> 里面专有的</font>，注意需要新的样式文件 <font color='red'>index.css</font> 。 



- main 盒子宽度为 980 像素，位置距离左边 220px (margin-left ) ，给高度就不用清除浮动
- main 里面包含左侧盒子，左浮动，<font color='red'>focus</font> 焦点图模块
- main 里面包含右侧盒子，右浮动，<font color='red'>newsflash</font> 新闻快报模块 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213047753.png" alt="image-20241224213047753" style="zoom:50%;" />



#### newsflash 新闻快报模块



- 1 号盒子为 news 新闻模块 高度为 165px
- 2 号盒子为 lifeservice 生活服务模块 高度为 209px
- 3 号盒子为 bargain 特价商品 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213141351.png" alt="image-20241224213141351" style="zoom:50%;" />



##### ⑴news 新闻模块



- 注意：这里我们分为上下两个模块，但是两个模块都用 div 
- 1 号盒子 <font color='red'>news-hd</font> 新闻头部模块，给一个高度和下边框 
- 2 号盒子<font color='red'> news-bd</font> 新闻主题部分，里面包含 ul 和 li 还有链接

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213224372.png" alt="image-20241224213224372" style="zoom:50%;" />



##### ⑵lifeservice 生活服务模块



- lifeservice 盒子宽度为 250 ，但是装不开里面的 4 个小 li 
- 可以让 lifeservice 里面的 ul 宽度为 252，就可以装的下 4 个 小 li
- ifeservice 盒子 overflow 隐藏多余的部分就可以了

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213356412.png" alt="image-20241224213356412" style="zoom: 50%;" />



### 2.7 推荐模块制作



![image-20241224213442054](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213442054.png)



- 大盒子 recom 推荐模块 recommend
- 里面包含 2 个盒子， 浮动即可
- 1 号盒子 recom_hd 
- 2 号盒子 recom_bd ，注意里面的小竖线



### 2.8 楼层区 floor 制作



注意这个 floor ，不要给高度，内容有多少，算多少

第一楼是家用电器模块： 里面包含两个盒子

- 1 号盒子 box_hd，给一个高度，有个下边框，里面分为左右 2 个盒子
- 2 号盒子 box_bd，不要给高度 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213619126.png" alt="image-20241224213619126" style="zoom:50%;" />



#### ①box_hd 模块



- 有高度可以不用清除浮动
- 左边 h3 ，盒子左浮动
- 右边 tab_list ，右浮动，因为用到 tab 切换效果，所以里面要用 ul 和 li 来做 

![image-20241224213825338](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213825338.png)



#### ②Tab栏原理-布局需求



要求选项卡个数要内容个数一致。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224213927616.png" alt="image-20241224213927616" style="zoom:50%;" />

#### ③box_bd 模块



- 根据 tab 切换的原理，<font color='red'> tab_content 里面包含 内容部分。 这个内容可以通过ul布局</font>
- 分为 5 个大列，列的宽度不一致

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241224214015800.png" alt="image-20241224214015800" style="zoom:50%;" />



## 3.品优购列表页制作



### 3.1 品优购列表页制作准备工作



1. 列表页面是新的页面，我们需要新建页面文件<font color='red'> list.html </font>。
2. 因为列表页的**<font color='red'>头部</font>**和**<font color='red'>底部</font>**基本一致，所以我们需要把首页中的头部和底部的结构复制过来。
3. 头部和底部的样式也需要，因此 list.html 中还需要引入 <font color='red'>common.css</font> 。
4. 需要新的 <font color='red'>list.css </font>样式文件，这是列表页专门的样式文件。



### 3.2 列表页 header 和 nav 修改



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229142438022.png" alt="image-20241229142438022" style="zoom:50%;" />



- 秒杀盒子 <font color='red'>sk（ second kill ）</font> 定位即可
- 1 号盒子左侧浮动 sk_list 里面包含 ul 和 li 
- 2 号盒子左侧浮动 sk_con 里面包含 ul 和 li



### 3.3 列表页主体 sk _container



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229142544471.png" alt="image-20241229142544471" style="zoom: 33%;" />

- 1 号盒子 sk _container 给宽度 1200，不要给高度
- 2 号盒子 sk_hd ，插入图片即可 
- 3 号盒子 sk_bd ，里面包含很多的 ul 和 li 



## 4. 品优购注册页制作



### 4.1 注册页类名命名



注册页面： register.html

注意：注册页面比较隐私，为了保护用户信息，我们不需要对当前页面做SEO优化。

| 名称     | 说明         |
| -------- | ------------ |
| 注册专区 | registerarea |
| 注册内容 | reg-form     |
| 错误的   | error        |
| 成功的   | success      |
| 默认的   | default      |



### 4.2 注册页布局



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229142810989.png" alt="image-20241229142810989" style="zoom:33%;" />



### 4.3 registerarea 布局



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229142835108.png" alt="image-20241229142835108" style="zoom:33%;" />



## 5. Web 服务器



### 5.1 什么是Web服务器



我们写的品优购网站，目前是放到自己电脑上的，只能自己访问浏览。

如果想要很多人访问我们的网站，可以把品优购放到服务器上，这样就可以多人访问我们的品优购网站了。



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229142930707.png" alt="image-20241229142930707" style="zoom:33%;" />



<font color='red'>服务器</font>（我们也会称之为主机）是提供计算服务的设备，**<font color='red'>它也是一台计算机</font>**。在网络环境下，根据服务器提供的服务类型不同，服务器又分为文件服务器、数据库服务器、应用程序服务器、<font color='red'>Web 服务器</font>等。

<font color='red'>Web 服务器一般指网站服务器</font>，是指驻留于因特网上某种类型计算机的程序，可以向浏览器等 Web 客户端提供文档，也可以放置网站文件，让全世界浏览；可以放置数据文件，让全世界下载。

以下服务器我们主要指的是Web服务器。

根据服务器在网络中所在的位置不同，又可分为<font color='red'>本地服务器</font>和<font color='red'>远程服务器</font>



### 5.2 本地服务器



我们可以把自己的电脑设置为本地服务器， 这样同一个局域网内的同学就可以访问你的品优购网站了。 就业班学ajax的时候，再进行讲解



### 5.3 远程服务器



本地服务器主要在局域网中访问，如果想要在互联网中访问，可以把品优购网站上传到远程服务器。

**<font color='red'>远程服务器</font>**是通常是别的公司为我们提供的一台电脑（主机），我们只要把网站项目上传到这台电脑上，任何人都可以利用<font color='red'>域名</font>访问我们的网站了。

比如域名： www.mi.com 可以访问小米网站

**总结：**

1. 服务器就是一台电脑。因为我们主要是做网站，所以我们主要使用web服务器
2. 服务器可以分为本地服务器和远程服务器
3. 远程服务器是别的公司为我们提供了一台计算机。
4. 我们可以把网站上传到远程服务器里面， 别人就可以通过域名访问我们的网站了。



### 5.4 将自己的网站上传到远程服务器



<font color='red'>注意：一般稳定的服务器都是需要收费的。 比如：阿里云</font>

这里给大家推荐一个免费的远程服务器（免费空间） http://free.3v.do/ 

1. 去免费空间网站注册账号。
2. 记录下主机名、用户名、密码、域名。
3. 利用 cutftp 软件 上传网站到远程服务器。
4. 在浏览器中输入域名，即可访问我们的品优购网站了。



------



# <font color='red'>课程总结</font>



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229143417476.png" alt="image-20241229143417476" style="zoom:50%;" />

1. HTML我们学的就是常用标签， 就是基本盒子
2. CSS 就是用来美化布局网页。
3. HTML+CSS是没有逻辑可言的，基本就是搭积木摆放盒子的过程，你需要的是耐心。
4. 对同学们来说，现在最困难的是 布局结构 。欠缺分析页面布局的能力, 
5. 同一个模块，有很多布局方式，能做出来就是好的。
6. 多看别人写的页面，模仿人家的布局，每次写页面总会有新的收获。
7. 错误总是在所难免，一定要学会利用chrome 调试工具， 他们能快速帮我们排查错误。你还需要细心。
8. 学好定位，对后面学习JavaScript 有很大的帮助。



------



# <font color='red'>CSS动画</font>



# 一、CSS3 2D转换



**<font color='red'>转换（transform）</font>**是CSS3中具有颠覆性的特征之一，可以实现元素的位移、旋转、缩放等效果

转换（transform）你可以简单理解为变形

- 移动：translate
- 旋转：rotate
- 缩放：scale



## 1. 二维坐标系



2D转换是改变标签在二维平面上的位置和形状的一种技术，先来学习二维坐标系

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229163500723.png" alt="image-20241229163500723" style="zoom:50%;" />



## 2. 2D 转换之移动 <font color='red'>translate</font>



2D移动是2D转换里面的一种功能，可以改变元素在页面中的位置，类似**<font color='red'>定位</font>**。<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229163555347.png" alt="image-20241229163555347" style="zoom:33%;" />



### 2.1 语法



```
transform: translate(x,y); 或者分开写
transform: translateX(n);
transform: translateY(n);
```



### 2.2 重点



- 定义 2D 转换中的移动，沿着 X 和 Y 轴移动元素
- translate最大的优点：不会影响到其他元素的位置
- translate中的百分比单位是相对于自身元素的 translate:(50%,50%);
- 对行内标签没有效果



## 3. 2D 转换之旋转<font color='red'> **rotate**</font>



2D旋转指的是让元素在2维平面内顺时针旋转或者逆时针旋转。<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229163754078.png" alt="image-20241229163754078" style="zoom:33%;" />

### 3.1 语法



```
transform:rotate(度数)
```



### 3.2  重点



- rotate里面跟度数， 单位是 deg 比如 rotate(45deg)
- 角度为正时，顺时针，负时，为逆时针
- 默认旋转的中心点是元素的中心点



### 3.3 案例：三角形



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229163925351.png" alt="image-20241229163925351" style="zoom: 50%;" />



```
p::before {
	content: '';
	position: absolute;
	right: 20px;
	top: 10px;
	width: 10px;
	height: 10px;
	border-right: 1px solid #000;
	border-bottom: 1px solid #000;
	transform: rotate(45deg);
}
```



## 4. 2D 转换中心点 <font color='red'>transform-origin</font>



我们可以设置元素转换的中心点



### 4.1  语法



```
transform-origin: x y;
```



### 4.2 重点



- 注意后面的参数 x 和 y 用<font color='red'>空格</font>隔开
- x y 默认转换的中心点是元素的中心点 (50% 50%)
- 还可以给x y 设置 像素 或者 方位名词 （top bottom left right center）



##  5. 2D 转换之缩放<font color='red'>**scale**</font>



缩放，顾名思义，可以放大和缩小。 只要给元素添加上了这个属性就能控制它放大还是缩小。<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229164153946.png" alt="image-20241229164153946" style="zoom:33%;" />

### 5.1 语法



```
transform:scale(x,y);
```



### 5.2 重点



- 注意其中的x和y用<font color='red'>逗号</font>分隔
- transform:scale(1,1) ：宽和高都放大一倍，相对于没有放大
- transform:scale(2,2) ：宽和高都放大了2倍
- transform:scale(2) ：只写一个参数，第二个参数则和第一个参数一样，相当于 scale(2,2)
- transform:scale(0.5,0.5)：缩小
- sacle缩放最大的优势：可以设置转换中心点缩放，默认以中心点缩放的，而且不影响其他盒子



## 6. 2D转换综合写法



**<font color='red'>注意：</font>**



- 同时使用多个转换，其格式为：transform: translate() rotate() scale() ...等，
- 其顺序会影转换的效果。（先旋转会改变坐标轴方向）
- **当我们同时有位移和其他属性的时候，记得要将位移放到最前**



## 7. 2D 转换总结



- 转换transform 我们简单理解就是变形 有2D 和 3D 之分
- 我们暂且学了三个 分别是 位移 旋转 和 缩放
- 2D 移动 translate(x, y) 最大的优势是不影响其他盒子， 里面参数用%，是相对于自身宽度和高度来计算的
- 可以分开写比如 translateX(x) 和 translateY(y)
- 2D 旋转 rotate(度数) 可以实现旋转元素 度数的单位是deg
- 2D 缩放 sacle(x,y) 里面参数是数字 不跟单位 可以是小数 最大的优势 不影响其他盒子
- 设置转换中心点 transform-origin : x y; 参数可以百分比、像素或者是方位名词
- 当我们进行综合写法，同时有位移和其他属性的时候，记得要将位移放到最前



# 二、CSS3动画



**<font color='red'>动画（animation）</font>**是CSS3中具有颠覆性的特征之一，可通过设置多个节点来精确控制一个或一组动画，常用来实现复杂的动画效果。

相比较过渡，动画可以实现更多变化，更多控制，连续自动播放等效果。



## 1. 动画的基本使用



制作动画分为两步：
1. 先定义动画
2. 再使用（调用）动画



### 1.1 用keyframes 定义动画（类似定义类选择器）



```
@keyframes 动画名称 {
	0%{
		width:100px;
	} 
	100%{
		width:200px;
	}
}
```



**动画序列**



- 0% 是动画的<font color='red'>开始</font>，100% 是动画的<font color='red'>完成</font>。这样的规则就是动画序列。
- 在 <font color='red'>@keyframes</font> 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果。
- 动画是使元素从一种样式逐渐变化为另一种样式的效果。您可以改变任意多的样式任意多的<font color='red'>次数</font>。
- 请用百分比来规定变化发生的时间，或用关键词 "<font color='red'>from</font>" 和 "<font color='red'>to</font>"，等同于<font color='red'> 0%</font> 和 <font color='red'>100%</font>。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229205955545.png" alt="image-20241229205955545" style="zoom:33%;" />



### 1.2 元素使用动画



```
div {
	width: 200px;
	height: 200px;
	background-color: aqua;
	margin: 100px auto;
	/* 调用动画 */
	animation-name: 动画名称;
	/* 持续时间 */
	animation-duration: 持续时间;
}
```



## 2. 动画常用属性



| 属性                      | 描述                                                         |
| :------------------------ | :----------------------------------------------------------- |
| @keyframes                | 规定动画                                                     |
| animation                 | 所有动画属性的简写属性，除了animation-play-state属性         |
| **animation-name**        | **规定@keyframes动画的名称（必须的）**                       |
| **animation-duration**    | **规定动画完成一个周期所花费的秒或毫秒，默认是0。（必须的）** |
| animation-timing-function | 规定动画的速度曲线，默认是“ease”。                           |
| animation-delay           | 规定动画何时开始，默认是0。                                  |
| animation-iteration-count | 规定动画被播放的次数，默认是1，还有infinite                  |
| animation-direction       | 规定动画是否在下一周期逆向播放，默认是“normal“,alternate逆播放 |
| animation-play-state      | 规定动画是否正在运行或暂停。默认是"running",还有"paused"。   |
| animation-fill-mode       | 规定动画结束后状态，保持forwards，回到起始backwards          |



##  3. 动画简写属性



animation：动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始或者结束的状态;



```
animation: myfirst 5s linear 2s infinite alternate;
```



- 简写属性里面不包含 animation-play-state 
- 暂停动画：animation-play-state: puased; 经常和鼠标经过等其他配合使用
- 想要动画走回来 ，而不是直接跳回来：animation-direction ： alternate
- 盒子动画结束后，停在结束位置： animation-fill-mode ： forwards



**案例：热点图案例**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229214421064.png" alt="image-20241229214421064" style="zoom:33%;" />



## 4.速度曲线细节



animation-timing-function：规定动画的速度曲线，默认是“ease”



| 值          | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| linear      | 动画从头到尾的速度是相同的。匀速                             |
| ease        | 默认。动画以低速开始，然后加快，在结束前变慢                 |
| ease-in     | 动画以低速开始                                               |
| ease-out    | 动画以低速结束                                               |
| ease-in-out | 动画以低速开始和结束                                         |
| steps()     | 指定了时间函数中的间隔数量（步长）；类似于像素进度条步进的效果 |



**案例：奔跑的熊大**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241229214751950.png" alt="image-20241229214751950" style="zoom:50%;" />



# 三、3D转换



我们生活的环境是3D的，照片就是3D物体在2D平面呈现的例子。



**有什么特点**                                            <img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230094945263.png" alt="image-20241230094945263" style="zoom:33%;" />

- 近大远小。
- 物体后面遮挡不可见



当我们在网页上构建3D效果的时候参考这些特点就能产出3D效果。



## 1. 三维坐标系



三维坐标系其实就是指立体空间，立体空间是由3个轴共同组成的。

- x轴：水平向右          <font color='red'>注意： x 右边是正值，左边是负值</font>
- y轴：垂直向下          <font color='red'>注意： y 下面是正值，上面是负值</font>
- z轴：垂直屏幕          <font color='red'>注意： 往外面是正值，往里面是负值</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095123300.png" alt="image-20241230095123300" style="zoom: 50%;" />



## 2. 3D移动 translate3d



3D移动在2D移动的基础上多加了一个可以移动的方向，就是z轴方向。



- translform:translateX(100px)：仅仅是在x轴上移动

- translform:translateY(100px)：仅仅是在Y轴上移动

- translform:translateZ(100px)：仅仅是在Z轴上移动（注意：<font color='red'>translateZ一般用px单位</font>）

- transform:translate3d(x,y,z)：其中 x、y、z 分别指要移动的轴的方向的距离

	

因为z轴是垂直屏幕，由里指向外面，所以默认是看不到元素在z轴的方向上移动



## 3. 透视 perspective



在2D平面产生近大远小视觉立体，但是只是效果二维的

- 如果想要在网页产生3D效果需要透视（理解成3D物体投影在2D平面内）。
- 模拟人类的视觉位置，可认为安排一只眼睛去看
- 透视我们也称为视距：视距就是人的眼睛到屏幕的距离
- 距离视觉点越近的在电脑平面成像越大，越远成像越小
- 透视的单位是像素



**<font color='red'>透视写在被观察元素的父盒子上面的</font>**

**<font color='red'>d</font>**：就是视距，视距就是一个距离人的眼睛到屏幕的距离。
**<font color='red'>z</font>**：就是 z轴，物体距离屏幕的距离，z轴越大（正值） 我们看到的物体就越大。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095413288.png" alt="image-20241230095413288" style="zoom:50%;" />



## 4. translateZ



translform:translateZ(100px)：仅仅是在Z轴上移动。

有了透视，就能看到translateZ 引起的变化了。

- translateZ：近大远小
- translateZ：往外是正值
- translateZ：往里是负值

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095459491.png" alt="image-20241230095459491" style="zoom:50%;" />



## 5. 3D旋转 rotate3d



3D旋转指可以让元素在三维平面内沿着 x轴，y轴，z轴或者自定义轴进行旋转。



**语法**

- transform:rotateX(45deg)：沿着x轴正方向旋转 45度
- transform:rotateY(45deg) ：沿着y轴正方向旋转 45deg
- transform:rotateZ(45deg) ：沿着Z轴正方向旋转 45deg
- transform:rotate3d(x,y,z,deg)： 沿着自定义轴旋转 deg为角度（了解即可）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095612169.png" alt="image-20241230095612169" style="zoom:50%;" />



对于元素旋转的方向的判断 我们需要先学习一个左手准则。

**左手准则**

- 左手的手拇指指向 x轴(y轴)的正方向
- 其余手指的弯曲方向就是该元素沿着x轴(y轴)旋转的方向

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095652246.png" alt="image-20241230095652246" style="zoom:33%;" /><img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095749642.png" alt="image-20241230095749642" style="zoom:33%;" />





**transform:rotate3d(x,y,z,deg)：** 沿着自定义轴旋转 deg为角度（了解即可）

>  xyz是表示旋转轴的矢量，是标示你是否希望沿着该轴旋转，最后一个标示旋转的角度。



- transform:rotate3d(1,0,0,45deg) 就是沿着x轴旋转 45deg
- transform:rotate3d(1,1,0,45deg) 就是沿着对角线旋转 45deg



## 6. 3D呈现 transfrom-style



- 控制子元素是否开启三维立体环境。。
- transform-style: flat; 子元素不开启3d立体空间 默认的
- transform-style: preserve-3d; 子元素开启立体空间
- <font color='red'>代码写给父级，但是影响的是子盒子</font>
- 这个属性很重要，后面必用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230095936727.png" alt="image-20241230095936727" style="zoom:50%;" />



## 7. 案例



### **两面翻转的盒子**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230152524697.png" alt="image-20241230152524697" style="zoom:33%;" />



**1. 搭建HTML结构**



```
<div class="box">
	<div class="front">黑马程序员</div>
	<div class=“back">pink老师等你</div>
</div>
```

- box父盒子里面包含前后两个子盒子
- box 是翻转的盒子 front是前面盒子 back是后面盒子



**2. CSS样式**



- box指定大小，切记要添加3d呈现
- back盒子要沿着Y轴翻转180度
- 最后鼠标经过box 沿着Y旋转180deg



### **3D导航栏**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20241230152637476.png" alt="image-20241230152637476" style="zoom:33%;" />



**1. 搭建HTML结构**



```
<ul>
	<li>
		<div class="box">
			<div class="front">黑马程序员</div>
			<div class="bottom">pink老师等你</div>
		</div>
	</li>
</ul>

```

- li 做导航栏
- .box 是翻转的盒子 front是前面盒子 bottom是底下盒子



**2. CSS样式**



- li设置大小，加透视和 3d呈现
- front 需要前移 17.5像素
- bottom 需要下移 17.5像素 并且要沿着x轴翻转 负90度
- 鼠标放到box 让盒子旋转90度



### 旋转木马



**1. 搭建HTML结构**



```
<section>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
	<div></div>
</section>

```



- 里面的6个div 分别是 6个狗狗图片
- 注意最终旋转是section标签 旋转



**2. CSS样式**



1. 给body添加 透视效果 perspective: 1000px;
2. 给section 添加 大小，一定不要忘记添加 3d呈现效果控制里面的6个div 
	- 别忘记子绝父相，section要加相对定位
3. 里面6个div 全部绝对定位叠到一起，然后移动不同角度旋转和距离
	- 注意：旋转角度用rotateY 距离 肯定用 translateZ来控制
4. 给section 添加动画animation ，让它可以自动旋转即可



# 四、浏览器私有前缀



浏览器私有前缀是为了兼容老版本的写法，比较新版本的浏览器无须添加



##  1.私有前缀



- -moz-：代表 firefox 浏览器私有属性
- -ms-：代表 ie 浏览器私有属性
- -webkit-：代表 safari、chrome 私有属性
- -o-：代表 Opera 私有属性



## 2.提倡的写法



以圆角属性为例

```
-moz-border-radius: 10px; 
-webkit-border-radius: 10px; 
-o-border-radius: 10px; 
border-radius: 10px;
```

