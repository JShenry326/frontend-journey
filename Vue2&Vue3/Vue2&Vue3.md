#    ***Vue 核心技术与实战***



# 一、Vue快速上手



## 1. Vue 概念



**Vue 是什么**



**概念**：Vue 是一个用于 <font color='red'>构建用户界面</font>① 的 <font color='red'>渐进式</font>② <font color='red'>框架</font>③

> ① 基于数据渲染出用户看到的页面
>
> ② 循序渐进
>
> ③ 一套完整的项目解决方案

①

​	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604213612384.png" alt="image-20250604213612384" style="zoom:50%;" />

②

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604213647179.png" alt="image-20250604213647179" style="zoom:50%;" />

**Vue 的两种使用方式：**

① Vue 核心包开发

**场景**：<font color='red'>局部</font> 模块改造

② Vue 核心包 & Vue 插件 工程化开发

**场景**：<font color='red'>整站</font> 开发



③

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604213814768.png" alt="image-20250604213814768" style="zoom:50%;" />

**优点**：大大提升开发效率 (<font color='red'>70%</font>↑)

**缺点**：需要理解记忆<font color='red'>规则</font> → 官网



## 2. 创建实例



**创建 Vue 实例，初始化渲染**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604213927403.png" alt="image-20250604213927403" style="zoom:50%;" />



## 3. 插值表达式



**插值表达式 {{ }}**



插值表达式是一种 Vue 的模板语法



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214010728.png" alt="image-20250604214010728" style="zoom:50%;" />



**<font color='red'>1. 作用:</font>** 利用表达式进行插值，渲染到页面中

表达式：是可以被求值的代码，JS引擎会将其计算出一个结果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214042349.png" alt="image-20250604214042349" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214049545.png" alt="image-20250604214049545" style="zoom:50%;" />

**<font color='red'>2. 语法：</font>**{{ 表达式 }}

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214127595.png" alt="image-20250604214127595" style="zoom:50%;" />

**<font color='red'>3.注意点：</font>**

（1）使用的数据必须存在 （data）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214147556.png" alt="image-20250604214147556" style="zoom:50%;" />

（2）支持的是表达式，而非语句，比如：if for ...

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214201766.png" alt="image-20250604214201766" style="zoom:50%;" />

（3）不能在标签属性中使用 {{ }} 插值

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214217779.png" alt="image-20250604214217779" style="zoom:50%;" />



## 4. 响应式特性



**Vue 核心特性：响应式**



我们已经掌握了基础的模板渲染，其实除了基本的模板渲染，Vue背后还做了大量工作。

比如：<font color='red'>数据的响应式处理</font> → 响应式：<font color='red'>数据变化，视图自动更新</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214330281.png" alt="image-20250604214330281" style="zoom: 50%;" />

如何访问 or 修改？data中的数据, 最终会被添加到实例上

① 访问数据：<font color='red'> "实例.属性名"</font>

② 修改数据： <font color='red'>"实例.属性名" = "值"</font>



数据改变，视图会自动更新

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214414214.png" alt="image-20250604214414214" style="zoom:50%;" />

<font color='red'>聚焦于数据 → 数据驱动视图</font>

使用 Vue 开发，关注<font color='red'>业务的核心逻辑</font>，根据业务<font color='red'>修改数据</font>即可



## 5. 开发者工具



**安装 Vue 开发者工具：装插件调试 Vue 应用**



（1）通过谷歌应用商店安装 （国外网站）

（2）极简插件: 下载 → 开发者模式 → 拖拽安装 → 插件详情允许访问文件	https://chrome.zzzmh.cn/index

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214526211.png" alt="image-20250604214526211" style="zoom:50%;" />



打开 Vue <font color='red'>运行的页面</font>，调试工具中 <font color='red'>Vue 栏</font>，即可查看<font color='red'>修改数据</font>，进行调试。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214552828.png" alt="image-20250604214552828" style="zoom:50%;" />



# 二、Vue 指令



## 1. Vue 指令



Vue 会根据不同的<font color='red'>【指令】</font>，针对标签实现不同的<font color='red'>【功能】</font>

指令：带有 <font color='red'>v- 前缀</font> 的 特殊 <font color='red'>标签属性</font>



## 2. v-html

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604214703051.png" alt="image-20250604214703051" style="zoom:50%;" />



**作用：**设置元素的 <font color='red'>innerHTML</font>

**语法：**v-html = "<font color='red'>表达式</font> "



## 3. v-show V.S. v-if



### v-show

1. **作用**： 控制元素显示隐藏
2. **语法**： v-show = "<font color='red'>表达式</font>"       表达式值 <font color='red'>true 显示</font>，<font color='red'> false 隐藏</font>
3. **原理**： <font color='red'>切换 display:none</font> 控制显示隐藏
4. **场景**： 频繁切换显示隐藏的场景

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215359384.png" alt="image-20250604215359384" style="zoom:50%;" />

### v-if

1. **作用**： 控制元素显示隐藏（<font color='red'>条件渲染</font>）
2. **语法**： v-if = "<font color='red'>表达式</font>"           表达式值 <font color='red'>true 显示， false 隐藏</font>
3. **原理**： 基于<font color='red'>条件判断</font>，是否 <font color='red'>创建</font> 或 <font color='red'>移除</font> 元素节点
4. **场景**： 要么显示，要么隐藏，不频繁切换的场景

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215514942.png" alt="image-20250604215514942" style="zoom:50%;" />



## 4. v-else & v-else-if



1. **作用**： 辅助 v-if 进行判断渲染
2. **语法**： v-else      v-else-if = "<font color='red'>表达式</font>"
3. **注意**： 需要紧挨着 v-if 一起使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215620611.png" alt="image-20250604215620611" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215655572.png" alt="image-20250604215655572" style="zoom:50%;" />



## 5. v-on



1. **作用**： 注册事件 <font color='red'>= 添加监听 + 提供处理逻辑</font>
2. **语法**：

  <font color='red'>① v-on:事件名 = "内联语句"</font>

  ② v-on:事件名 = "methods中的函数名"

3. **简写**：<font color='red'>@事件名</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215819975.png" alt="image-20250604215819975" style="zoom:50%;" />

4. **注意**：methods函数内的 <font color='red'>this 指向 Vue 实例</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215849185.png" alt="image-20250604215849185" style="zoom:33%;" /><img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604215905469.png" alt="image-20250604215905469" style="zoom:50%;" />    



### 5.1 v-on 调用传参



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220024263.png" alt="image-20250604220024263" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220034041.png" alt="image-20250604220034041" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220100588.png" alt="image-20250604220100588" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220107985.png" alt="image-20250604220107985" style="zoom:50%;" />



## 6. v-bind



1. **作用**： 动态的设置html的<font color='red'>标签属性 </font>  → src url title ...
2. **语法**： v-bind:<font color='red'>属性名</font>="表达式"
3. **注意**： 简写形式 :<font color='red'>属性名="表达式"</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220211343.png" alt="image-20250604220211343" style="zoom:50%;" />



## 图片切换案例-波仔学习之旅



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220312501.png" alt="image-20250604220312501" style="zoom:50%;" />

**核心思路分析**：

① 数组存储图片路径 →<font color='red'> [ 图片1， 图片2， 图片3， ... ]</font>
② 准备下标 index，<font color='red'>数组[下标]</font> → <font color='red'>v-bind</font> 设置 <font color='red'>src</font> 展示图片 → <font color='red'>修改下标切换图片</font>



## 7. v-for



1. **作用**： 基于<font color='red'>数据</font>循环，<font color='red'> 多次</font>渲染整个元素   → <font color='red'>数组</font>、对象、数字...

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220417712.png" alt="image-20250604220417712" style="zoom:50%;" />

2. **遍历数组语法**：

	

	v-for = "(<font color='red'>item, index</font>) in <font color='red'>数组</font>"

	- <font color='red'>item</font> 每一项，<font color='red'> index</font> 下标
	- 省略 index: v-for = "<font color='red'>item in 数组</font>"



## 图书管理案例 - 小黑的书架



**明确需求：**

① 基本渲染   <font color='red'>→ v-for</font>

② 删除功能   <font color='red'>→</font> 用<font color='red'> filter</font> 根据<font color='red'> id</font> 从数组中删除对应项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220640056.png" alt="image-20250604220640056" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220646450.png" alt="image-20250604220646450" style="zoom:50%;" />



## 8. v-for 中的 key



**语法：**<font color='red'>key属性 = "唯一标识"</font>

**作用：**给列表项添加的<font color='red'>唯一标识</font>。便于Vue进行列表项的<font color='red'>正确排序复用</font>。

**注意点：**

1. key 的值只能是 <font color='red'>字符串</font> 或 <font color='red'>数字类型</font>
2. key 的值必须具有 <font color='red'>唯一性</font>
3. 推荐使用 <font color='red'>id</font> 作为 key（唯一），不推荐使用 <font color='red'>index</font> 作为 key（会变化，不对应）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220955303.png" alt="image-20250604220955303" style="zoom:50%;" />



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220734690.png" alt="image-20250604220734690" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220813536.png" alt="image-20250604220813536" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220822887.png" alt="image-20250604220822887" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220830298.png" alt="image-20250604220830298" style="zoom:50%;" />



## 9. v-for 中的 key - 不加 key



v-for 的默认行为会尝试 <font color='red'>原地修改元素</font> （<font color='red'>就地复用</font>）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220903426.png" alt="image-20250604220903426" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604220917374.png" alt="image-20250604220917374" style="zoom:50%;" />



## 10. v-model



1. **作用:** 给 <font color='red'>表单元素</font> 使用, <font color='red'>双向数据绑定</font>   → 可以快速 <font color='red'>获取</font> <font color='red'>或 设置</font> 表单元素内容

  ① 数据变化 → 视图自动更新
  ② <font color='red'>视图</font>变化 →<font color='red'> 数据</font>自动更新

2. **语法**: v-model = '变量

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604221136784.png" alt="image-20250604221136784" style="zoom:50%;" />



# 综合案例 - 小黑记事本



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250604221212255.png" alt="image-20250604221212255" style="zoom:50%;" />

**功能需求：**

① 列表渲染
② 删除功能
③ 添加功能
④ 底部统计 和 清空



**功能总结：**

① 列表渲染：

<font color='red'>v-for key</font> 的设置 {{ }} 插值表达式

② 删除功能

<font color='red'>v-on</font> 调用传参 <font color='red'>filter</font> 过滤 覆盖修改原数组

③ 添加功能

<font color='red'>v-model</font> 绑定 <font color='red'>unshift</font> 修改原数组添加

④ 底部统计 和 清空

数组.length累计长度
覆盖数组清空列表
<font color='red'>v-show</font> 控制隐藏



# 三、指令补充



## 1. 指令修饰符



通过<font color='red'> "."</font> 指明一些指令 <font color='red'>后缀</font>，不同 <font color='red'>后缀</font> 封装了不同的处理操作 → 简化代码

① **按键修饰符**

- <font color='red'>@keyup.enter</font> → 键盘回车监听

② **v-model修饰符**

- <font color='red'>v-model.trim</font> → 去除首尾空格
- <font color='red'>v-model.number</font> → 转数字

③ **事件修饰符**

- @事件名.stop → 阻止冒泡
- @事件名.prevent → 阻止默认行为

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103528971.png" alt="image-20250605103528971" style="zoom:50%;" />



## 2. v-bind对于样式操作的增强



为了方便开发者进行<font color='red'>样式控制</font>， Vue 扩展了 <font color='red'>v-bind </font>的语法，可以针对 <font color='red'>class 类名</font> 和<font color='red'> style 行内样式</font> 进行控制

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103636207.png" alt="image-20250605103636207" style="zoom:50%;" />



### 2.1 操作class



**语法** ：	<font color='red'>:class = "对象/数组"</font>



① <font color='red'>对象</font> → 键就是类名，值是布尔值。如果值为 <font color='red'>true</font>，有这个类，否则没有这个类

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103714004.png" alt="image-20250605103714004" style="zoom:50%;" />

适用场景：一个类名，来回切换		<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103726874.png" alt="image-20250605103726874" style="zoom:50%;" />



②<font color='red'> 数组</font> → 数组中所有的类，都会添加到盒子上，本质就是一个 <font color='red'>class 列表</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103759369.png" alt="image-20250605103759369" style="zoom:50%;" />

适用场景：批量添加或删除类			<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103811000.png" alt="image-20250605103811000" style="zoom:50%;" />



### 案例：京东秒杀 tab 导航高亮



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103834740.png" alt="image-20250605103834740" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605103841921.png" alt="image-20250605103841921" style="zoom:50%;" />

**核心思路：**

1. 基于数据动态渲染 tab → <font color='red'>v-for</font>
2. 准备下标记录高亮的是哪一个 tab → <font color='red'>activeIndex</font>
3. 基于下标，动态控制 class 类名 → <font color='red'>v-bind:class</font>

<font color='red'>所谓切换高亮，其实就是改下标</font>



### 2.2 操作style



**语法** ：	<font color='red'>:style = "样式对象"</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605104019017.png" alt="image-20250605104019017" style="zoom:50%;" />

**适用场景**：某个具体属性的动态设置

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605104035453.png" alt="image-20250605104035453" style="zoom:50%;" />



## 3. v-model应用于其他表单元素



常见的表单元素都可以用 v-model 绑定关联 → 快速 <font color='red'>获取</font> 或 <font color='red'>设置 </font>表单元素的值

它会根据<font color='red'> 控件类型</font> 自动选取 <font color='red'>正确的方法</font> 来更新元素

- <font color='red'>输入框 input:text</font>			 → value

- 文本域 textarea			  → value

- 复选框 input:checkbox	       → checked

- 单选框 input:radio  	            → checked

- 下拉菜单 select			  → value

	...

	

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605104308741.png" alt="image-20250605104308741" style="zoom:50%;" />



# 四、computed 计算属性



## 1. 基础语法



**计算属性**

**概念**：基于<font color='red'>现有的数据</font>，计算出来的<font color='red'>新属性</font>。 <font color='red'>依赖</font>的数据变化，<font color='red'>自动</font>重新计算。

**语法**：

1. 声明在 <font color='red'>computed 配置项</font>中，一个计算属性对应一个函数
2. 使用起来和普通属性一样使用 {{ <font color='red'>计算属性名</font> }}

计算属性 → 可以将一段 <font color='red'>求值的代码</font> 进行封装

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605200122432.png" alt="image-20250605200122432" style="zoom:50%;" />



## 2. 计算属性 vs 方法



**computed 计算属性 vs methods 方法**



**computed 计算属性：**

**作用**：封装了一段对于<font color='red'>数据</font>的处理，求得一个<font color='red'>结果</font>。

**语法**：

1. 写在 <font color='red'>computed</font> 配置项中
2. 作为属性，直接使用 → <font color='red'>this.计算属性</font> {{ <font color='red'>计算属性</font> }}

> <font color='red'>**缓存特性**（提升性能）</font>：
>
> 计算属性会对计算出来的<font color='red'>结果缓存</font>，再次使用直接读取缓存，
> 依赖项变化了，会<font color='red'>自动</font>重新计算 → 并<font color='red'>再次缓存</font>



**methods 方法：**

**作用**：给实例提供一个<font color='red'>方法</font>，调用以处理<font color='red'>业务逻辑</font>。

**语法**：

1. 写在<font color='red'> methods </font>配置项中
2. 作为方法，需要调用 → <font color='red'>this.方法名( )</font> {{ <font color='red'>方法名()</font> }} @事件名="<font color='red'>方法名</font>"



## 3. 计算属性完整写法



计算属性默认的简写，只能读取访问，<font color='red'>不能 "修改"</font>。

如果要<font color='red'> "修改" </font>→ 需要写计算属性的<font color='red'>完整写法</font>。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605105323216.png" alt="image-20250605105323216" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605105331369.png" alt="image-20250605105331369" style="zoom:50%;" />



## 综合案例 - 成绩案例



需求说明：
1. 渲染功能
2. 删除功能
3. 添加功能
4. 统计总分，求平均分

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605105412240.png" alt="image-20250605105412240" style="zoom:50%;" />



**业务技术点总结：**
1. 渲染功能（不及格高亮）
  - <font color='red'>v-if v-else</font> 	v-for 	<font color='red'>v-bind:class</font>
2. 删除功能
  - 点击传参 filter过滤覆盖原数组
  - <font color='red'>.prevent </font>阻止默认行为
3. 添加功能
  - v-model 	<font color='red'>v-model修饰符(.trim .number)</font>
  - <font color='red'>unshift</font> 修改数组更新视图
4. 统计总分，求平均分
  - <font color='red'>计算属性</font> reduce求和



# 五、watch 侦听器



## 1. 基础语法



**watch 侦听器（监视器）**



**作用**：<font color='red'>监视数据变化</font>，执行一些 业务逻辑 或 异步操作。

**语法**：

1. <font color='red'>简单写法 → 简单类型数据，直接监视</font>
2. 完整写法 → 添加额外配置项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605105943559.png" alt="image-20250605105943559" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605105950747.png" alt="image-20250605105950747" style="zoom:50%;" />

2. 完整写法 → 添加额外<font color='red'>配置项</font>

	(1)<font color='red'> deep: true</font> 对复杂类型深度监视

	> `deep: true` 让 Vue **深度递归监听复杂类型的子属性变化**，否则默认只监听对象/数组的引用变化。
	
	(2) <font color='red'>immediate: true</font> 初始化页面立刻执行一次handler方法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605110034779.png" alt="image-20250605110034779" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605110048997.png" alt="image-20250605110048997" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605110105623.png" alt="image-20250605110105623" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605110116523.png" alt="image-20250605110116523" style="zoom:50%;" />



# 综合案例：水果购物车



**需求说明：**

1. 渲染功能
2. 删除功能
3. 修改个数
4. 全选反选
5. 统计 <font color='red'>选中的</font> 总价 和 总数量
6. 持久化到本地

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250605110202280.png" alt="image-20250605110202280" style="zoom:50%;" />

**业务技术点总结：**

1. 渲染功能：<font color='red'> v-if/v-else</font> 	<font color='red'>v-for</font> 	<font color='red'>:class</font>
2. 删除功能:  <font color='red'>点击传参</font>           <font color='red'>filter</font>过滤覆盖原数组
3. 修改个数：<font color='red'>点击传参</font>          <font color='red'>find</font>找对象
4. 全选反选：计算属性<font color='red'>computed</font>       完整写法 <font color='red'>get/set</font>
5. 统计选中的总价和总数量: 计算属性<font color='red'>computed</font> <font color='red'>reduce</font>条件求和
6. 持久化到本地： <font color='red'>watch</font>监视，<font color='red'>localStorage</font>，<font color='red'>JSON.stringify</font>, <font color='red'>JSON.parse</font>



# 六、生命周期



## 1. Vue 生命周期 & 生命周期四个阶段



**思考：**什么时候可以发送<font color='red'>初始化渲染请求</font>？（越早越好） 什么时候可以开始<font color='red'>操作dom</font>？（至少dom得渲染出来）

**Vue生命周期：**一个Vue实例从 <font color='red'>创建 </font>到 <font color='red'>销毁</font> 的整个过程。

**生命周期四个阶段：**① 创建 ② 挂载 ③ 更新 ④ 销毁

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164610842.png" alt="image-20250606164610842" style="zoom:50%;" />



## 2. Vue 生命周期函数（钩子函数）



Vue生命周期过程中，会<font color='red'>自动运行一些函数</font>font>，被称为<font color='red'>【生命周期钩子】</font>→ 让开发者可以在<font color='red'>【特定阶段】</font>运行<font color='red'>自己的代码</font>。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164716411.png" alt="image-20250606164716411" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164741520.png" alt="image-20250606164741520" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164755721.png" alt="image-20250606164755721" style="zoom:50%;" />



## 3. Vue 生命周期钩子案例 - 新闻列表 & 输入框自动聚焦

## 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164815922.png" alt="image-20250606164815922" style="zoom:50%;" />



# 综合案例：小黑记账清单



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164858944.png" alt="image-20250606164858944" style="zoom:50%;" />

**案例总结：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606164911889.png" alt="image-20250606164911889" style="zoom:50%;" />



# 七、工程化开发入门



## 1. 工程化开发 & 脚手架 Vue CLI



**开发 Vue 的两种方式：**

1. 核心包传统开发模式：基于 html / css / js 文件，直接引入核心包，开发 Vue。
2. <font color='red'>工程化开发模式：基于构建工具（例如：webpack ) 的环境中开发 Vue。</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165015542.png" alt="image-20250606165015542" style="zoom:50%;" />

问题：
① webpack 配置<font color='red'>不简单</font>
② <font color='red'>雷同</font>的基础配置
③ 缺乏<font color='red'>统一标准</font>

<font color='red'>需要一个工具，生成标准化的配置！</font>



**基本介绍：**

Vue CLI 是 Vue 官方提供的一个<font color='red'>全局命令工具</font>。

可以帮助我们<font color='red'>快速创建</font>一个开发 Vue 项目的<font color='red'>标准化基础架子</font>。【集成了 webpack 配置】

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165154912.png" alt="image-20250606165154912" style="zoom:50%;" />

**好处：**

1. 开箱即用，零配置
2. 内置 babel 等工具
3. 标准化



**使用步骤：**

1. 全局安装 (一次) ：<font color='red'>yarn global add @vue/cli </font>或 <font color='red'>npm i @vue/cli -g</font>
2. 查看 Vue 版本：<font color='red'>vue --version</font>
3. 创建项目架子：<font color='red'>vue create project-name</font>（项目名-不能用中文）
4. 启动项目：<font color='red'> yarn serve </font>或 <font color='red'>npm run serve</font>（找package.json）



## 2. 脚手架目录文件介绍 & 项目运行流程



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165515367.png" alt="image-20250606165515367" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165529795.png" alt="image-20250606165529795" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165541918.png" alt="image-20250606165541918" style="zoom:50%;" />



## 3. 组件化开发 & 根组件



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606165632042.png" alt="image-20250606165632042" style="zoom:50%;" />

① **组件化**：一个页面可以拆分成<font color='red'>一个个组件</font>，每个组件有着自己独立的<font color='red'>结构、样式、行为</font>。

好处：便于<font color='red'>维护</font>，利于<font color='red'>复用</font> → 提升<font color='red'>开发效率</font>。

组件分类：普通组件、根组件。

② **根组件**：整个应用最上层的组件，包裹所有普通小组件。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606170127127.png" alt="image-20250606170127127" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606170143701.png" alt="image-20250606170143701" style="zoom:50%;" />



### 3.1 App.vue 文件（单文件组件）的三个组成部分



1. **语法高亮插件：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606170307886.png" alt="image-20250606170307886" style="zoom:50%;" />

2. **三部分组成：**

- template：结构 （有且只能一个根元素）
- script: js逻辑
- style： 样式 (可支持less，需要装包)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606170733099.png" alt="image-20250606170733099" style="zoom:50%;" />



3. **让组件支持 less**

（1） style标签，lang="less" 开启less功能

（2） 装包:<font color='red'> yarn add less less-loader</font>



## 4. 普通组件的注册使用



**组件注册的两种方式：**

1. <font color='red'>局部注册：只能在注册的组件内使用</font>

  ① 创建 .vue 文件 (三个组成部分)
  ② 在使用的组件内导入并注册

2. 全局注册：所有组件内都能使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171008378.png" alt="image-20250606171008378" style="zoom:50%;" />

**使用：**

◆ 当成 html 标签使用<font color='red'> `<组件名></组件名>`</font>

**注意:** 

◆ 组件名规范 → 大驼峰命名法，如：HmHeader

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171144558.png" alt="image-20250606171144558" style="zoom:50%;" />



2. <font color='red'>全局注册：所有组件内都能使用</font>

  ① 创建 .vue 文件 (三个组成部分)

  ② <font color='red'>main.js</font> 中进行全局注册

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171318659.png" alt="image-20250606171318659" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171353854.png" alt="image-20250606171353854" style="zoom:50%;" />

**使用：**

◆ 当成 html 标签使用<font color='red'> `<组件名></组件名>`</font>

**注意:** 

◆ 组件名规范 → 大驼峰命名法，如：HmHeader



------



**技巧：**

◆ 一般都用<font color='red'>局部注册</font>，如果发现确实是<font color='red'>通用组件</font>，再定义到全局。



# 综合案例：小兔鲜首页



## 1. 小兔鲜首页 - 组件拆分



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171521317.png" alt="image-20250606171521317" style="zoom:50%;" />

**页面开发思路：**

1. 分析页面，<font color='red'>按模块拆分组件</font>，搭架子<font color='red'> (局部或全局注册)</font>
2. 根据设计图，编写组件 html 结构 css 样式 (已准备好)
3. 拆分封装<font color='red'>通用小组件 (局部或全局注册)</font>

将来 → 通过 js 动态渲染，实现功能

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250606171540480.png" alt="image-20250606171540480" style="zoom:50%;" />



# 八、组件的三大组成部分 (结构/样式/逻辑)



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609154304209.png" alt="image-20250609154304209" style="zoom:50%;" />



## 1. 组件的样式冲突 scoped



**默认情况**：写在组件中的样式会 <font color='red'>全局生效</font> → 因此很容易造成多个组件之间的样式冲突问题。

1. <font color='red'>全局样式</font>: 默认组件中的样式会作用到全局
2. <font color='red'>局部样式</font>: 可以给组件加上 <font color='red'>scoped</font> 属性, <font color='red'>可以让样式只作用于当前组件</font>



**scoped原理？**

1. 当前组件内标签都被添加 <font color='red'>data-v-hash值</font> 的属性
2. css选择器都被添加<font color='red'> [data-v-hash值] </font>的属性选择器

最终效果: <font color='red'>必须是当前组件的元素,</font> 才会有这个自定义属性, 才会被这个样式作用到

​					<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609160553539.png" alt="image-20250609160553539" style="zoom:50%;" /><img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609160600748.png" alt="image-20250609160600748" style="zoom:50%;" />



## 2. data 是一个函数



一个组件的 <font color='red'>data</font> 选项必须是一个<font color='red'>函数</font>。→ 保证每个组件实例，维护<font color='red'>独立</font>的一份数据对象。

每次创建新的组件实例，都会新执行一次 data 函数，得到一个新对象。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609160657898.png" alt="image-20250609160657898" style="zoom:50%;" />



# 九、组件通信



## 1. 什么是组件通信



组件通信, 就是指 <font color='red'>组件与组件</font> 之间的<font color='red'>数据传递</font>

- 组件的数据是<font color='red'>独立</font>的，无法直接访问其他组件的数据。
- 想用其他组件的数据 → 组件通信

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609160929997.png" alt="image-20250609160929997" style="zoom:50%;" />



## 2. 不同的组件关系 和 组件通信方案分类



### 2.1 组件关系分类：



1. <font color='red'>父子关系</font>
2. 非父子关系

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161052374.png" alt="image-20250609161052374" style="zoom:50%;" />



### 2.2 组件通信解决方案：



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161133901.png" alt="image-20250609161133901" style="zoom:50%;" />



### 2.3 父子通信流程图：



1. 父组件通过 <font color='red'>props </font>将数据传递给子组件
2. 子组件利用 <font color='red'>$emit</font> 通知父组件修改更新

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161222432.png" alt="image-20250609161222432" style="zoom:50%;" />



### 2.4 父 → 子



父组件通过 <font color='red'>props</font> 将数据传递给子组件

① 父中给子添加属性传值 ② 子props 接收 ③ 子组件使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161308459.png" alt="image-20250609161308459" style="zoom: 67%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161315364.png" alt="image-20250609161315364" style="zoom:50%;" />



### 2.5 子 → 父



子组件利用 <font color='red'>$emit</font> 通知父组件，进行修改更新

① 子 $emit 发送消息 ②父中给子添加消息监听 ③ 父中实现处理函数

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161430612.png" alt="image-20250609161430612" style="zoom: 67%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161446075.png" alt="image-20250609161446075" style="zoom:50%;" />



## 3. 什么是 prop



**Prop 定义：**<font color='red'>组件上</font> 注册的一些 <font color='red'>自定义属性</font>

**Prop 作用：**向子组件传递数据



**特点：**

- 可以 传递 <font color='red'>任意数量</font> 的prop
- 可以 传递<font color='red'> 任意类型</font> 的prop

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161831184.png" alt="image-20250609161831184" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161838217.png" alt="image-20250609161838217" style="zoom:50%;" />



## 4. props 校验



**思考：**组件的 prop 可以乱传么？

**作用：**为组件的 prop 指定<font color='red'>验证要求</font>，不符合要求，控制台就会有<font color='red'>错误提示</font> → 帮助开发者，快速发现错误

**语法：**

<font color='red'>① 类型校验</font>
② 非空校验
③ 默认值
④ 自定义校验

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161943516.png" alt="image-20250609161943516" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609161955281.png" alt="image-20250609161955281" style="zoom:50%;" />



## 5. prop & data、单向数据流



**共同点：**都可以给组件提供数据。

**区别：**

- data 的数据是<font color='red'>自己</font>的 → 随便改
- prop 的数据是<font color='red'>外部</font>的 → 不能直接改，要遵循 <font color='red'>单向数据流</font>

单向数据流：父级 prop 的数据更新，会向下流动，影响子组件。这个数据流动是单向的。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162100516.png" alt="image-20250609162100516" style="zoom:50%;" />

> [!CAUTION]
>
> **口诀：**谁的数据谁负责



# 综合案例：小黑记事本 (组件版)



**组件通信案例：小黑记事本 - 组件版**



需求说明：

① 拆分基础组件
② 渲染待办任务
③ 添加任务
④ 删除任务
⑤ 底部合计 和 清空功能
⑥ 持久化存储

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162216775.png" alt="image-20250609162216775" style="zoom:50%;" />

**核心步骤：**

① 拆分基础组件

新建组件 → 拆分存放结构 → 导入注册使用

② 渲染待办任务

提供数据<font color='red'>(公共父组件)</font> →<font color='red'> 父传子</font>传递 list → v-for 渲染

③ 添加任务

收集数据 v-model → 监听事件 → <font color='red'>子传父</font>传递任务 → 父组件 unshift

④ 删除任务

监听删除携带 id → <font color='red'>子传父</font>传递 id → 父组件 filter 删除

⑤ 底部合计 和 清空功能

底部合计：<font color='red'>父传子</font>传递 list → 合计展示
清空功能：监听点击 → <font color='red'>子传父</font>通知父组件 → 父组件清空

⑥ 持久化存储：watch监视数据变化，持久化到本地



## 非父子通信 (拓展) 



### 1. event bus 事件总线



**作用：**非父子组件之间，进行简易消息传递。(复杂场景 → Vuex)

1. 创建一个都能访问到的事件总线 (空 Vue 实例) → utils/EventBus.js 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162430762.png" alt="image-20250609162430762" style="zoom:50%;" />

2. A 组件(接收方)，监听 Bus 实例的事件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162444315.png" alt="image-20250609162444315" style="zoom:50%;" />

3. B 组件(发送方)，触发 Bus 实例的事件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162457320.png" alt="image-20250609162457320" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162505241.png" alt="image-20250609162505241" style="zoom:50%;" />



### 2. provide & inject



**provide & inject 作用：**<font color='red'>跨层级</font>共享数据。

1. 父组件 provide 提供数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162553639.png" alt="image-20250609162553639" style="zoom:50%;" />

2. 子/孙组件 inject 取值使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162609354.png" alt="image-20250609162609354" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162615928.png" alt="image-20250609162615928" style="zoom:50%;" />



# 十、进阶语法



## 1. v-model 原理



**原理：**v-model本质上是一个<font color='red'>语法糖</font>。例如应用在输入框上，就是 <font color='red'>value属性</font> 和 <font color='red'>input事件</font> 的合写。

**作用：**提供数据的双向绑定

- 数据变，视图跟着变 <font color='red'>:value</font> 
- 视图变，数据跟着变 <font color='red'>@input</font>

**注意**：<font color='red'>$event</font> 用于在模板中，获取事件的形参，相当于事件对象 e

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162836252.png" alt="image-20250609162836252" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609162843690.png" alt="image-20250609162843690" style="zoom:50%;" />



## 2. 表单类组件封装 & v-model 简化代码



***1.*** 表单类组件 <font color='red'>封装</font> → 实现 子组件 和 父组件数据 的<font color='red'>双向绑定</font>

① <font color='red'>父传子</font>：数据 应该是父组件 <font color='red'>props</font> 传递 过来的，<font color='red'>拆解 v-model</font> 绑定数据

② <font color='red'>子传父</font>：监听输入，子传父传值给父组件修改

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163028759.png" alt="image-20250609163028759" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163037070.png" alt="image-20250609163037070" style="zoom:50%;" />

***2.*** 父组件 v-model <font color='red'>简化代码</font>，实现 子组件 和 父组件数据 <font color='red'>双向绑定</font>

① 子组件中：props 通过 <font color='red'>value</font> 接收，事件触发 <font color='red'>input</font>

② 父组件中：<font color='red'>v-model</font> 给组件直接绑数据 <font color='red'>( :value + @input )</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163413882.png" alt="image-20250609163413882" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163421165.png" alt="image-20250609163421165" style="zoom:50%;" />



## 3. .sync 修饰符



**作用：**可以实现 <font color='red'>子组件</font> 与 <font color='red'>父组件数据</font> 的 <font color='red'>双向绑定</font>，简化代码

**特点：**prop属性名，可以<font color='red'>自定义</font>，非固定为 <font color='red'>value</font>

**场景：**封装弹框类的基础组件，<font color='red'> visible属性</font> true显示 false隐藏

**本质：**就是 <font color='red'>:属性名</font> 和 <font color='red'>@update:属性名</font> 合写

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163611027.png" alt="image-20250609163611027" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163617969.png" alt="image-20250609163617969" style="zoom: 50%;" />



## 4. ref 和 $refs



**作用：**利用 ref 和 $refs 可以用于<font color='red'> 获取 dom 元素</font>, 或 <font color='red'>组件实例</font>

**<font color='red'>特点：</font>**查找范围 → <font color='red'>当前组件内 (更精确稳定)</font>

① 获取 dom：

1. 目标标签 – 添加 ref 属性

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163724665.png" alt="image-20250609163724665" style="zoom:50%;" />

2. 恰当时机（dom元素加载完之后）, 通过 this.$refs.xxx, 获取目标标签

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163740046.png" alt="image-20250609163740046" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163750240.png" alt="image-20250609163750240" style="zoom:50%;" />

就可以<font color='red'>调用组件对象里面的方法</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163837214.png" alt="image-20250609163837214" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163843811.png" alt="image-20250609163843811" style="zoom:50%;" />



## 5. Vue异步更新、$nextTick



**需求：编辑标题, 编辑框自动聚焦**

1. 点击编辑，显示编辑框
2. 让编辑框，<font color='red'>立刻获取焦点</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163911249.png" alt="image-20250609163911249" style="zoom:50%;" />

问题："显示之后"，立刻获取焦点是不能成功的！

<font color='red'>**原因：**Vue 是 异步更新 DOM (提升性能)</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609163935162.png" alt="image-20250609163935162" style="zoom:50%;" />

**$nextTick：**<font color='red'>等 DOM 更新后</font>, 才会触发执行此方法里的函数体

语法:  this.$nextTick(函数体)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250609164025244.png" alt="image-20250609164025244" style="zoom:50%;" />



# 十一、自定义指令



**自定义指令：**自己定义的指令, 可以<font color='red'>封装一些 dom 操作</font>， 扩展额外功能



> 思考：
>
> <img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135202311.png" alt="image-20250610135202311" style="zoom:50%;" />
>
> 每个指令有着自己各自独立的功能



## 1. 基本语法 (全局&局部注册)



**需求:** 当页面加载时，让元素将获得焦点

**问题：**<font color='red'>(autofocus 在 safari 浏览器有兼容性)</font>

**解决：**操作dom：dom元素.focus()

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135518463.png" alt="image-20250610135518463" style="zoom:50%;" />



- **全局注册 - 语法**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135352766.png" alt="image-20250610135352766" style="zoom:50%;" />

<font color='red'>inserted </font>为指令的生命周期钩子，表示<font color='red'>当指令所绑定的元素被添加到页面当中的时候，会自动调用</font>



- **局部注册 – 语法**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135404875.png" alt="image-20250610135404875" style="zoom:50%;" />

- **使用：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135535669.png" alt="image-20250610135535669" style="zoom:50%;" />



## 2. 指令的值



**需求：**实现一个 color 指令 - 传入不同的颜色, 给标签设置文字颜色

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135736821.png" alt="image-20250610135736821" style="zoom:50%;" />

**语法：**在绑定指令时，可以通过“等号”的形式为指令 绑定 <font color='red'>具体的参数值</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135641916.png" alt="image-20250610135641916" style="zoom:50%;" />

通过 <font color='red'>binding.value</font> 可以拿到指令值，指令值修改会 <font color='red'>触发 update 函数</font>。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135654106.png" alt="image-20250610135654106" style="zoom:50%;" />



**指令值的语法：**

- <font color='red'>v-指令名 = "指令值"</font>，通过 等号 可以绑定指令的值
- 通过<font color='red'> binding.value</font> 可以拿到指令的值
- 通过<font color='red'> update 钩子</font>，可以监听指令值的变化，进行dom更新操作



## 3. v-loading 指令封装



**场景：**实际开发过程中，发送<font color='red'>请求需要时间</font>，在请求的数据未回来时，页面会处于<font color='red'>空白状态</font> => <font color='red'>用户体验不好</font>



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610135919842.png" alt="image-20250610135919842" style="zoom:50%;" />

**需求：**封装一个 v-loading 指令，实现加载中的效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610140031040.png" alt="image-20250610140031040" style="zoom:50%;" />

**分析：**

1. 本质 loading 效果就是一个蒙层，盖在了盒子上
2. 数据请求中，开启loading状态，添加蒙层
3. 数据请求完毕，关闭loading状态，移除蒙层

**实现：**

1. 准备一个 loading 类，通过伪元素定位，设置宽高，实现蒙层
2. 开启关闭 loading 状态（添加移除蒙层），本质只需要添加移除类即可
3. 结合自定义指令的语法进行封装复用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610140052218.png" alt="image-20250610140052218" style="zoom:50%;" />



# 十二、插槽



## 1. 默认插槽



**作用：**让组件内部的一些 <font color='red'>结构</font> 支持<font color='red'> 自定义</font>

**需求:** 将需要多次显示的对话框, 封装成一个组件

**问题：**组件的内容部分，<font color='red'>不希望写死</font>，希望能使用的时候<font color='red'>自定义</font>。怎么办？

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610140220376.png" alt="image-20250610140220376" style="zoom:50%;" />



**插槽基本语法：**

1. 组件内需要定制的结构部分，改用`<slot></slot>`占位
2. 使用组件时, `<MyDialog></MyDialog>`标签内部, 传入结构替换slot

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610140250598.png" alt="image-20250610140250598" style="zoom:50%;" />



## 2. 后备内容（默认值）



通过插槽完成了内容的定制，传什么显示什么, 但是如果不传，则是空白

能否给插槽设置 <font color='red'>默认显示内容</font> 呢？

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610140330713.png" alt="image-20250610140330713" style="zoom:50%;" />



**插槽后备内容：**封装组件时，可以为预留的<font color='red'> `<slot>`</font> 插槽提供<font color='red'>后备内容</font>（默认内容）。

**语法:** 在 `<slot>` 标签内，放置内容, 作为默认显示内容

**效果:**

- 外部使用组件时，不传东西，则slot会显示后备内容

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610141309609.png" alt="image-20250610141309609" style="zoom:50%;" />

- 外部使用组件时，传东西了，则slot整体会被换掉

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610141317028.png" alt="image-20250610141317028" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610141325108.png" alt="image-20250610141325108" style="zoom:50%;" />



## 3. 具名插槽



**需求：**一个组件内有多处结构，需要外部传入标签，进行定制

**默认插槽：**一个的定制位置

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154138055.png" alt="image-20250610154138055" style="zoom:50%;" />

**具名插槽语法:**

1. 多个slot使用name属性区分名字

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154157380.png" alt="image-20250610154157380" style="zoom:50%;" />

2. template配合v-slot:名字来分发对应标签

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154211299.png" alt="image-20250610154211299" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154231485.png" alt="image-20250610154231485" style="zoom:50%;" />



**具名插槽简化语法:**



1. 多个slot使用name属性区分名字

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154304715.png" alt="image-20250610154304715" style="zoom:50%;" />

2. template配合v-slot:名字来分发对应标签

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154319051.png" alt="image-20250610154319051" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154348874.png" alt="image-20250610154348874" style="zoom:50%;" />

<font color='red'>v-slot:插槽名</font> 可以简化成 <font color='red'>\#插槽名</font>



## 4. 作用域插槽



**作用域插槽:** 定义 slot 插槽的同时, 是可以<font color='red'>传值</font>的。给 <font color='red'>插槽</font> 上可以<font color='red'> 绑定数据</font>，将来<font color='red'> 使用组件时可以用</font>。

**场景：**封装表格组件

1. 父传子，动态渲染表格内容
2. 利用默认插槽，定制操作列
3. 删除或查看都需要用到 <font color='red'>当前项的 id</font>，属于 <font color='red'>组件内部的数据</font>，通过 <font color='red'>作用域插槽</font> 传值绑定，进而使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154504330.png" alt="image-20250610154504330" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154511928.png" alt="image-20250610154511928" style="zoom:50%;" />

**基本使用步骤：**

1. 给 slot 标签, 以 添加属性的方式传值

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154528751.png" alt="image-20250610154528751" style="zoom:50%;" />

2. 所有添加的属性, 都会被收集到一个对象中

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154541217.png" alt="image-20250610154541217" style="zoom:50%;" />

3. 在template中, 通过 <font color='red'>#插槽名= "obj" </font>接收，默认插槽名为 <font color='red'>default</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154554242.png" alt="image-20250610154554242" style="zoom:50%;" />



# 综合案例：商品列表



**需求说明：**

1. my-tag 标签组件封装

  (1) 双击显示输入框，输入框获取焦点
  (2) 失去焦点，隐藏输入框
  (3) 回显标签信息
  (4) 内容修改，回车 → 修改标签信息

  

2. my-table 表格组件封装

  (1) 动态传递表格数据渲染
  (2) 表头支持用户自定义
  (3) 主体支持用户自定义

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154718120.png" alt="image-20250610154718120" style="zoom:50%;" />

**小结**

商品列表的实现封装了几个组件？

- 2个组件，标签组件 和 表格组件

封装用到的核心技术点有哪些？

- props父传子 $emit子传父 v-model
- `$nextTick` 自定义指令
- 插槽：具名插槽，作用域插槽



# 十三、路由入门



## 1. 单页应用程序: SPA - Single Page Application

 

**单页面应用(SPA):** 所有功能在 <font color='red'>一个html页面</font> 上实现

**具体示例:** 网易云音乐 https://music.163.com/

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610154924997.png" alt="image-20250610154924997" style="zoom:50%;" />



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155025768.png" alt="image-20250610155025768" style="zoom:50%;" />

> SEO：搜索引擎优化



单页面应用程序，之所以开发效率高，性能高，用户体验好

最大的原因就是：<font color='red'>页面按需更新</font>

要按需更新，首先就需要明确：<font color='red'>访问路径</font> 和 <font color='red'>组件</font> 的对应关系！

访问路径 和 组件的对应关系如何确定呢？ <font color='red'>路由</font>



## 2. 路由概念



**生活中的路由：**设备和ip的映射关系

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155207815.png" alt="image-20250610155207815" style="zoom:50%;" />



**Vue中路由：**<font color='red'>路径 和 组件</font> 的 <font color='red'>映射</font> 关系

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155234862.png" alt="image-20250610155234862" style="zoom:50%;" />



## 3. VueRouter



### 3.1 VueRouter 的 介绍



**目标：**认识插件 VueRouter，掌握 VueRouter 的基本使用步骤

**作用：**修改地址栏路径时，切换显示匹配的组件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155335723.png" alt="image-20250610155335723" style="zoom: 50%;" />

**说明：**Vue 官方的一个路由插件，是一个第三方包

**官网：**https://v3.router.vuejs.org/zh/

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155320118.png" alt="image-20250610155320118" style="zoom:50%;" />



### 3.2 VueRouter 的 使用 (5 + 2)



**5个基础步骤 (固定)**

① 下载： 下载 VueRouter 模块到当前工程，版本3.6.5

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155642197.png" alt="image-20250610155642197" style="zoom:50%;" />

② 引入

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155649654.png" alt="image-20250610155649654" style="zoom:50%;" />

③ 安装注册

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155704416.png" alt="image-20250610155704416" style="zoom:50%;" />

④ 创建路由对象

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155716953.png" alt="image-20250610155716953" style="zoom:50%;" />

⑤ 注入，将路由对象注入到new Vue实例中，建立关联

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155729065.png" alt="image-20250610155729065" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155737631.png" alt="image-20250610155737631" style="zoom:50%;" />



**2 个核心步骤**



① 创建需要的组件 (views目录)，配置路由规则

Find.vue 	My.vue 	Friend.vue

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155810153.png" alt="image-20250610155810153" style="zoom:50%;" />

② 配置导航，配置路由出口(路径匹配的组件显示的位置)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155825523.png" alt="image-20250610155825523" style="zoom:50%;" />



## 4. 组件存放目录问题



**注意：**<font color='red'>.vue文件</font> 本质无区别。

路由相关的组件，为什么放在 views 目录呢？	<font color='red'>组件分类</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155923519.png" alt="image-20250610155923519" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610155930996.png" alt="image-20250610155930996" style="zoom:50%;" />



### 4.1 组件分类



**组件分类：** .vue文件分2类； 页面组件 & 复用组件

**注意：**都是 <font color='red'>.vue文件 (本质无区别)</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610160021948.png" alt="image-20250610160021948" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610160609721.png" alt="image-20250610160609721" style="zoom:50%;" />

分类开来 更易维护

src/views文件夹

- <font color='red'>页面组件</font> - 页面展示 - 配合路由用

src/components文件夹

- <font color='red'>复用组件 </font>- 展示数据 - 常用于复用

	

**小练习：**以下 .vue 文件，属于什么分类组件？应该放在哪个目录?

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610160635234.png" alt="image-20250610160635234" style="zoom:50%;" />

<font color='red'>页面组件 </font>配合路由用，放在 views 目录

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250610160658217.png" alt="image-20250610160658217" style="zoom:50%;" />

<font color='red'>复用组件</font>，放在 components 目录



# 十四、路由进阶



## 1. 路由模块封装



**路由的封装抽离**



**问题：**所有的路由配置都堆在main.js中合适么？

**目标：**将路由模块抽离出来。 

**好处：**<font color='red'>拆分模块，利于维护</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612150530096.png" alt="image-20250612150530096" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612150540720.png" alt="image-20250612150540720" style="zoom:50%;" />

<font color='red'>**绝对路径：**@指代src目录，可以用于快速引入组件</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612162338927.png" alt="image-20250612162338927" style="zoom:50%;" />



## 2. 声明式导航 & 导航高亮



**声明式导航 - 导航链接**



**需求：**实现导航高亮效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612150731702.png" alt="image-20250612150731702" style="zoom:50%;" />

vue-router 提供了一个全局组件 **router-link** (取代 a 标签)

① <font color='red'>能跳转</font>，配置 to 属性指定路径(<font color='red'>必须</font>) 。本质还是 a 标签 ，<font color='red'>to 无需 #</font>

②<font color='red'> 能高亮</font>，默认就会提供<font color='red'>高亮类名</font>，可以直接设置高亮样式

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612150853719.png" alt="image-20250612150853719" style="zoom:50%;" />



## 3. 精确匹配&模糊匹配



**声明式导航 - 两个类名**



**说明：**我们发现 router-link 自动给当前导航添加了<font color='red'> 两个高亮类名</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612150944931.png" alt="image-20250612150944931" style="zoom:50%;" />

**① router-link-active** <font color='red'>模糊匹配 (用的多)</font>

to="/my" 可以匹配 /my /my/a /my/b .... 

**② router-link-exact-active** <font color='red'>精确匹配</font>

to="/my" 仅可以匹配 /my

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151026642.png" alt="image-20250612151026642" style="zoom:50%;" />

> 模糊匹配应用场景：一级目录下还有二级目录，点击二级目录一级目录依然高亮



## 4. 自定义高亮类名



**说明：**router-link 的<font color='red'> 两个高亮类名 太长了</font>，我们希望能定制怎么办？

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151057782.png" alt="image-20250612151057782" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151105398.png" alt="image-20250612151105398" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151114277.png" alt="image-20250612151114277" style="zoom:50%;" />

**如何自定义 router-link 的 两个高亮类名？**

- linkActiveClass 模糊匹配 类名自定义
- linkExactActiveClass 精确匹配 类名自定义



## 5. 声明式导航传参 ( 查询参数传参 & 动态路由传参 )



**声明式导航 - 跳转传参**

**目标：**在跳转路由时, 进行传值

1. 查询参数传参
2. 动态路由传参

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151227201.png" alt="image-20250612151227201" style="zoom:50%;" />

**<font color='red'>1. 查询参数传参</font>**



**语法格式如下**

- to="/path<font color='red'>?参数名=值</font>"

**对应页面组件接收传递过来的值**

- $route.<font color='red'>query.参数名</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151412121.png" alt="image-20250612151412121" style="zoom:50%;" />



**<font color='red'>2. 动态路由传参</font>**



① 配置动态路由

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151513337.png" alt="image-20250612151513337" style="zoom:50%;" />

② 配置导航链接

- to="/path<font color='red'>/参数值</font>"

③ 对应页面组件接收传递过来的值

- $route.<font color='red'>params.参数名</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151600655.png" alt="image-20250612151600655" style="zoom:50%;" />



**两种传参方式的区别**

1. 查询参数传参 (比较适合传<font color='red'>多个参数</font>)

  ① 跳转：to="/path<font color='red'>?参数名=值&参数名2=值</font>"
  ② 获取：$route.query.参数名

2. 动态路由传参 (<font color='red'>优雅简洁</font>，传<font color='red'>单个参数</font>比较方便)

  ① 配置动态路由：path: "/path/:参数名"
  ② 跳转：to="/path<font color='red'>/参数值</font>"
  ③ 获取：$route.params.参数名



**动态路由参数可选符**



**问题：**配了路由 <font color='red'>path: "/search/:words"</font> 为什么按下面步骤操作，会未匹配到组件，显示空白？

**原因：** /search/:words 表示，必须要传参数。如果不传参数，也希望匹配，可以加个可选符 <font color='red'>"?"</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151827263.png" alt="image-20250612151827263" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151834686.png" alt="image-20250612151834686" style="zoom:50%;" />



## 6. 路由重定向



**Vue路由 - 重定向**



**问题：**网页打开， url 默认是 / 路径，未匹配到组件时，会出现空白

**说明：**重定向 → 匹配path后, 强制跳转path路径

**<font color='red'>语法：</font>** { path: 匹配路径, redirect: 重定向到的路径 },

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151950561.png" alt="image-20250612151950561" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612151957348.png" alt="image-20250612151957348" style="zoom:50%;" />



## 7. 路由 - 404



**Vue路由 - 404**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152046600.png" alt="image-20250612152046600" style="zoom:50%;" />

**作用：**当路径找不到匹配时，给个提示页面

**位置：**配在路由最后

**语法：**path: "*" (任意路径) – 前面不匹配就命中最后这个

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152058293.png" alt="image-20250612152058293" style="zoom:50%;" />



## 8. 路由模式



**Vue路由 - 模式设置**



**问题:** 路由的路径看起来不自然, 有#，能否切成真正路径形式?

- hash路由(默认) 例如: http://localhost:8080/#/home
- history路由(常用) 例如: http://localhost:8080/home (以后上线需要服务器端支持)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152149280.png" alt="image-20250612152149280" style="zoom:50%;" />



## 9. 编程式导航



**编程式导航 - 基本跳转**



**问题：**点击按钮跳转如何实现？

**编程式导航：**用JS代码来进行跳转

**两种语法:**

① path 路径跳转
② name 命名路由跳转

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152246995.png" alt="image-20250612152246995" style="zoom:50%;" />

<font color='red'>① path 路径跳转 (简易方便)</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152310664.png" alt="image-20250612152310664" style="zoom:50%;" />

<font color='red'>② name 命名路由跳转 (适合 path 路径长的场景)</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152341886.png" alt="image-20250612152341886" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152348895.png" alt="image-20250612152348895" style="zoom:50%;" />



## 10. 编程式导航传参 ( 查询参数传参 & 动态路由传参 )



**编程式导航 - 路由传参**



**问题：**点击搜索按钮，跳转需要传参如何实现？

两种传参方式：查询参数 + 动态路由传参

<font color='red'>两种跳转方式，对于两种传参方式都支持：</font>

① path 路径跳转传参
② name 命名路由跳转传参

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152452116.png" alt="image-20250612152452116" style="zoom:50%;" />



<font color='red'>① path 路径跳转传参</font>

**query传参**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152524767.png" alt="image-20250612152524767" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152531157.png" alt="image-20250612152531157" style="zoom:50%;" />

**动态路由传参 (需要配动态路由)**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152606818.png" alt="image-20250612152606818" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152626164.png" alt="image-20250612152626164" style="zoom:50%;" />



<font color='red'>② name 命名路由跳转传参</font>

**query传参**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152651615.png" alt="image-20250612152651615" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152659200.png" alt="image-20250612152659200" style="zoom:50%;" />

**动态路由传参 (需要配动态路由)**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152714287.png" alt="image-20250612152714287" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152727573.png" alt="image-20250612152727573" style="zoom:50%;" />



# 面经基础版



## 1. 案例效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152923941.png" alt="image-20250612152923941" style="zoom:50%;" />

<font color='red'>分析：配路由 + 实现功能</font>

1. 配路由

  ① 首页 和 面经详情，两个一级路由
  ② 首页内嵌四个可切换页面 (<font color='red'>嵌套二级路由</font>)

2. 实现功能

  ① 首页请求渲染
  ② <font color='red'>跳转传参</font> 到 详情页，详情页渲染
  ③ <font color='red'>组件缓存</font>，优化性能

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612152956553.png" alt="image-20250612152956553" style="zoom:50%;" />



## 2. 组件缓存 keep-alive



**问题：**从面经 点到 详情页，又点返回，数据重新加载了 → 希望回到原来的位置

**原因：**路由跳转后，组件被销毁了，返回回来组件又被重建了，所以数据重新被加载了

**解决：**利用 keep-alive 将组件缓存下来

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153034213.png" alt="image-20250612153034213" style="zoom:50%;" />



**1. keep-alive是什么**

keep-alive 是 Vue 的内置组件，当它包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。

keep-alive 是一个抽象组件：它自身不会渲染成一个 DOM 元素，也不会出现在父组件链中。

**2. keep-alive的优点**

在组件切换过程中 把切换出去的组件保留在内存中，防止重复渲染DOM，减少加载时间及性能消耗，提高用户体验性。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153118399.png" alt="image-20250612153118399" style="zoom:50%;" />

**问题：**缓存了所有被切换的组件



**3. keep-alive的三个属性**



①<font color='red'> include </font>： 组件名数组，只有匹配的组件会被缓存
② exclude ： 组件名数组，任何匹配的组件都不会被缓存
③ max ： 最多可以缓存多少组件实例

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153152344.png" alt="image-20250612153152344" style="zoom:50%;" />

**4. keep-alive的使用会触发两个生命周期函数**



activated 当组件<font color='red'>被激活（使用）</font>的时候触发 → 进入这个页面的时候触发

deactivated 当组件<font color='red'>不被使用</font>的时候触发 → 离开这个页面的时候触发

**组件缓存后就不会执行组件的created, mounted, destroyed 等钩子了**

所以其提供了<font color='red'>actived</font> 和 <font color='red'>deactived</font>钩子，帮我们实现业务需求。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153254045.png" alt="image-20250612153254045" style="zoom:50%;" />



## 3. 自定义创建项目



**目标：**基于 VueCli 自定义创建项目架子

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153412331.png" alt="image-20250612153412331" style="zoom:50%;" />



## 4. ESlint 代码规范



**目标：**认识代码规范

**代码规范：**一套写代码的约定规则。例如："赋值符号的左右是否需要空格" "一句结束是否是要加;" ... 老话说："<font color='red'>没有规矩不成方圆</font>" → 正规的团队 需要 <font color='red'>统一</font>的编码风格

JavaScript Standard Style 规范说明 https://standardjs.com/rules-zhcn.html
下面是这份规则中的一小部分：

- 字符串使用单引号 'abc'
- 无分号 const name = 'zs'
- 关键字后加空格 if (name = 'ls') { ... }
- 函数名后加空格 function name (arg) { ... }
- 坚持使用全等 === 摒弃 ==
- ...



## 5. 代码规范错误



**目标：**学会解决代码规范错误

如果你的代码不符合 standard 的要求，<font color='red'>ESlint</font> 会跳出来刀子嘴，豆腐心地提示你。

**比如：**在main.js中随意做一些改动，添加一些分号，空行

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612153616420.png" alt="image-20250612153616420" style="zoom:50%;" />

**两种解决方案：**

① 手动修正

根据错误提示来一项一项<font color='red'>手动</font>修改纠正。

如果你不认识命令行中的语法报错是什么意思，根据错误代码去 [ESLint 规则表] ([规则参考 - ESLint - 插件化的 JavaScript 代码检查工具](https://zh-hans.eslint.org/docs/latest/rules/))中查找其具体含义

② 自动修正

基于 vscode 插件 ESLint <font color='red'>高亮错误</font>，并<font color='red'>通过配置 自动</font> 帮助我们<font color='red'>修复</font>错误。


<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612154002115.png" alt="image-20250612154002115" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250612154009194.png" alt="image-20250612154009194" style="zoom:50%;" />



# 十五、vuex



## 1. vuex概述



目标：明确 vuex 是什么，应用场景，优势

1. **是什么：**

  vuex([Vuex 是什么？ | Vuex](https://v3.vuex.vuejs.org/zh/)) 是一个 vue 的 <font color='red'>状态管理工具</font>，状态就是数据。

  大白话：vuex 是一个插件，可以帮我们管<font color='red'>理 vue 通用的数据 (多组件共享的数据)</font>，例如：购物车数据 个人信息数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613124828004.png" alt="image-20250613124828004" style="zoom:50%;" />

2. **场景：**

  ① 某个状态 在 <font color='red'>很多个组件</font> 来使用 (个人信息)

  ② 多个组件 <font color='red'>共同维护</font> 一份数据 (购物车)

  

3. **优势：**

  ① 共同维护一份数据，<font color='red'>数据集中化管理</font>

  ② <font color='red'>响应式变化</font>

  ③ 操作简洁 (vuex提供了一些辅助函数)


<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613124838736.png" alt="image-20250613124838736" style="zoom:50%;" />



## 2. 构建 vuex [多组件数据共享] 环境



**目标：**基于脚手架创建项目，构建 vuex 多组件数据共享环境

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125033765.png" alt="image-20250613125033765" style="zoom:50%;" />

效果是三个组件, 共享一份数据:

- 任意一个组件都可以修改数据
- 三个组件的数据是同步的



## 3. 创建一个空仓库



**目标：**安装 vuex 插件，初始化一个空仓库

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125208821.png" alt="image-20250613125208821" style="zoom:50%;" />

1. yarn add vuex@3

2. 新建 store/index.js 专门存放 vuex

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125126739.png" alt="image-20250613125126739" style="zoom:50%;" />

3. Vue.use(Vuex)

  创建仓库 new Vuex.Store()

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125139856.png" alt="image-20250613125139856" style="zoom:50%;" />

4. 在 main.js 中导入挂载到 Vue 实例上

​	检验：<font color='red'>this.$store</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125155882.png" alt="image-20250613125155882" style="zoom:50%;" />



## 4. 核心概念



### 4.1 state 状态



**目标：**明确如何给仓库 <font color='red'>提供</font> 数据，如何 <font color='red'>使用</font> 仓库的数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125321434.png" alt="image-20250613125321434" style="zoom:50%;" />

**1. 提供数据：**



State 提供唯一的公共数据源，所有共享的数据都要统一放到 Store 中的 State 中存储。

在 state 对象中可以添加我们要共享的数据。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125329413.png" alt="image-20250613125329413" style="zoom:50%;" />

**2. 使用数据：**



<font color='red'>① 通过 store 直接访问</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125420460.png" alt="image-20250613125420460" style="zoom:50%;" />

<font color='red'>② 通过辅助函数 (简化)</font>

**mapState**是辅助函数，帮助我们把 store中的数据 <font color='red'>自动</font> 映射到 组件的计算属性中

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125522971.png" alt="image-20250613125522971" style="zoom:50%;" />



### 4.2 mutations



**目标：明确 vuex 同样遵循单向数据流，组件中不能直接修改仓库的数据**



通过 strict: true 可以开启严格模式

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125639565.png" alt="image-20250613125639565" style="zoom:50%;" />

this.$store.state.count++ <font color='red'>(错误写法)</font>



**目标：掌握 mutations 的操作流程，来修改 state 数据。 (state数据的修改只能通过 mutations )**



1. 定义 mutations 对象，对象中存放修改 state 的方法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125734710.png" alt="image-20250613125734710" style="zoom:50%;" />

2. 组件中提交调用 mutations

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125748811.png" alt="image-20250613125748811" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125756197.png" alt="image-20250613125756197" style="zoom:50%;" />



**目标：掌握 mutations 传参语法**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130127890.png" alt="image-20250613130127890" style="zoom:50%;" />

提交 mutation 是可以传递参数的 <font color='red'>this.$store.commit( 'xxx', 参数 )</font>

1. 提供 mutation 函数 (带参数 - 提交载荷 payload )

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125935933.png" alt="image-20250613125935933" style="zoom:50%;" />

2. 页面中提交调用 mutation

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613125952111.png" alt="image-20250613125952111" style="zoom:50%;" />

> [!NOTE]
>
> Tips: 提交参数只能一个，如果有多个参数，包装成一个对象传递，store文件中使用obj.对象名来接受

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130107536.png" alt="image-20250613130107536" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250614161542352.png" alt="image-20250614161542352" style="zoom:50%;" />



**mutations - 练习**



**目标：**减法功能，巩固 mutations 传参语法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130203078.png" alt="image-20250613130203078" style="zoom:50%;" />

**目标：**实时输入，实时更新，巩固 mutations 传参语法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130216997.png" alt="image-20250613130216997" style="zoom:50%;" />



### 4.3 辅助函数 - mapMutations



**目标：**掌握辅助函数 mapMutations，映射方法

mapMutations 和 mapState很像，它是把位于<font color='red'>mutations中的方法</font>提取了出来，映射到<font color='red'>组件methods</font>中

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130359064.png" alt="image-20250613130359064" style="zoom:50%;" />



### 4.4 actions



**目标：**明确 actions 的基本语法，处理异步操作。

**需求:** 一秒钟之后, 修改 state 的 count 成 666。

**说明：**<font color='red'>mutations 必须是同步的 (便于监测数据变化，记录调试)</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130450876.png" alt="image-20250613130450876" style="zoom:50%;" />



### 4.3 辅助函数 - mapActions



mapActions 是把位于 <font color='red'>actions中的方法</font>提取了出来，映射到<font color='red'>组件methods</font>中

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130547648.png" alt="image-20250613130547648" style="zoom:50%;" />



### 4.5 getters



**目标：**掌握核心概念 getters 的基本语法 (类似于计算属性)

**说明：**除了state之外，有时我们还需要从state中<font color='red'>派生出一些状态</font>，这些状态是依赖state的，此时会用到getters

**例如：**state中定义了list，为 1-10 的数组，组件中，需要显示所有大于5的数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130656119.png" alt="image-20250613130656119" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130708572.png" alt="image-20250613130708572" style="zoom:50%;" />



### 4.6 模块 module (进阶语法)



**目标：掌握核心概念 module 模块的创建**



由于 vuex 使用<font color='red'>单一状态树</font>，应用的所有状态<font color='red'>会集中到一个比较大的对象</font>。当应用变得非常复杂时，store 对象就有可能变得相当臃肿。(当项目变得越来越大的时候，Vuex会变得越来越难以维护)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130758392.png" alt="image-20250613130758392" style="zoom:50%;" />



**模块拆分：**

user模块: store/modules/user.js

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130913573.png" alt="image-20250613130913573" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613130919937.png" alt="image-20250613130919937" style="zoom:50%;" />



**目标：掌握模块中 state 的访问语法**



尽管已经分模块了，但其实子模块的状态，还是会挂到根级别的 state 中，属性名就是模块名

使用模块中的数据：

① 直接通过模块名访问 <font color='red'>$store.state.模块名.xxx</font>

② 通过 mapState 映射

- 默认根级别的映射 <font color='red'>mapState([ 'xxx' ])</font>
- 子模块的映射<font color='red'> mapState('模块名', ['xxx'])</font> - 需要开启命名空间

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131111070.png" alt="image-20250613131111070" style="zoom:50%;" />



**目标：掌握模块中 getters 的访问语法**



使用模块中 getters 中的数据：

① 直接通过模块名访问<font color='red'> $store.getters['模块名/xxx ']</font>

② 通过 mapGetters 映射

- 默认根级别的映射 <font color='red'>mapGetters([ 'xxx' ])</font>
- 子模块的映射 <font color='red'>mapGetters('模块名', ['xxx'])</font> - 需要开启命名空间

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131213498.png" alt="image-20250613131213498" style="zoom:50%;" />



**目标：掌握模块中 mutation 的调用语法**



**注意：**默认模块中的 mutation 和 actions 会被挂载到全局，<font color='red'>需要开启命名空间</font>，才会挂载到子模块。

调用子模块中 mutation：

① 直接通过 store 调用 <font color='red'>$store.commit('模块名/xxx ', 额外参数)</font>

② 通过 mapMutations 映射

- 默认根级别的映射 <font color='red'>mapMutations([ 'xxx' ])</font>
- 子模块的映射 <font color='red'>mapMutations('模块名', ['xxx'])</font> - 需要开启命名空间

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131303225.png" alt="image-20250613131303225" style="zoom: 50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131314254.png" alt="image-20250613131314254" style="zoom:50%;" />



**目标：掌握模块中 action 的调用语法 (同理 - 直接类比 mutation 即可)**



**注意：**默认模块中的 mutation 和 actions 会被挂载到全局，<font color='red'>需要开启命名空间</font>，才会挂载到子模块。

调用子模块中 action ：

① 直接通过 store 调用<font color='red'> $store.dispatch('模块名/xxx ', 额外参数)</font>

② 通过 mapActions 映射

- 默认根级别的映射 <font color='red'>mapActions([ 'xxx' ])</font>
- 子模块的映射 <font color='red'>mapActions('模块名', ['xxx'])</font> - 需要开启命名空间

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131403963.png" alt="image-20250613131403963" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131410515.png" alt="image-20250613131410515" style="zoom:50%;" />

# 综合案例 - 购物车



## 1. 功能分析，创建项目，构建分析基本结构



1. 功能模块分析
① 请求动态渲染购物车，<font color='red'>数据存 vuex</font>
② 数字框控件 <font color='red'>修改数据</font>
③ <font color='red'>动态计算</font> 总价和总数量

2. 脚手架新建项目 (注意：勾选vuex)
vue create vue-cart-demo
3. 将原本src内容清空，替换成素材的《vuex-cart-准备代码》并分析

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131502966.png" alt="image-20250613131502966" style="zoom:50%;" />



## 2. 构建 cart 购物车模块



**说明：**既然明确数据要存 vuex，建议分模块存，购物车数据存 cart 模块，将来还会有 user 模块，article 模块...

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131556093.png" alt="image-20250613131556093" style="zoom:50%;" />



## 3. 基于 json-server 工具，准备后端接口服务环境



1. 安装全局工具 <font color='red'>json-server</font> （全局工具仅需要安装一次）【官网：[json-server - npm](https://www.npmjs.com/package/json-server)】
    <font color='red'>yarn global add json-server 或 npm i json-server -g</font>
2. 代码根目录新建一个 db 目录
3. 将资料 index.json 移入 db 目录
4. 进入 db 目录，执行命令，启动后端接口服务
    <font color='red'>json-server index.json</font>
5. 访问接口测试 http://localhost:3000/cart

**推荐：**<font color='red'> json-server --watch index.json(可以实时监听 json 文件的修改)</font> 

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131733507.png" alt="image-20250613131733507" style="zoom:50%;" />



## 4. 请求获取数据存入 vuex, 映射渲染



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131759220.png" alt="image-20250613131759220" style="zoom:50%;" />



## 5. 修改数量功能完成



**注意：**前端 vuex 数据，后端数据库数据都要更新

![image-20250613131831510](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613131831510.png)



## 6. 底部 getters 统计



1. 提供 getters

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613132024800.png" alt="image-20250613132024800" style="zoom:50%;" />

2. 使用 getters

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613132035913.png" alt="image-20250613132035913" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250613132045356.png" alt="image-20250613132045356" style="zoom:50%;" />



# 智慧商城项目



## 1. 项目演示



**目标：**查看项目效果，明确功能模块 → 完整的电商购物流程

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615172329903.png" alt="image-20250615172329903" style="zoom:50%;" />



## 2. 项目收获



**目标：**明确做完本项目，能够收获哪些内容

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615172353857.png" alt="image-20250615172353857" style="zoom:50%;" />



## 4. 创建项目



**目标：**基于 VueCli 自定义创建项目架子

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615172423276.png" alt="image-20250615172423276" style="zoom:50%;" />



## 5. 调整初始化目录



**目标：**将目录调整成符合企业规范的目录

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615172448364.png" alt="image-20250615172448364" style="zoom:50%;" />

1. 删除 多余的文件
2. 修改 路由配置 和 App.vue
3. 新增 两个目录 api / utils
① api 接口模块：发送ajax请求的接口模块
② utils 工具模块：自己封装的一些工具方法模块



## 6. vant 组件库



**目标：**认识第三方 Vue组件库 vant-ui

**组件库：**第三方 封装 好了很多很多的 组件，整合到一起就是一个组件库。

[Vant 4 - 轻量、可定制的移动端组件库](https://vant-ui.github.io/vant/#/zh-CN)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615172530468.png" alt="image-20250615172530468" style="zoom:50%;" />



### 6.1 其他 Vue 组件库



**目标：**了解其他 Vue 组件库

Vue的组件库并不是唯一的，vant-ui 也仅仅只是组件库的一种。

一般会按照不同平台进行分类：

1. PC端： 

	- element-ui([Element - 网站快速成型工具](https://element.eleme.cn/#/zh-CN)) (element-plus) 

	- ant-design-vue([Ant Design Vue](https://2x.antdv.com/docs/vue/introduce-cn))

2. 移动端：

	- vant-ui 

	- Mint UI (饿了么) ([Mint UI](https://mint-ui.github.io/#!/zh-cn))

	- Cube UI (滴滴)([cube-ui Document](https://didi.github.io/cube-ui/#/zh-CN))

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173046632.png" alt="image-20250615173046632" style="zoom:50%;" />



### 6.2 vant 全部导入 和 按需导入



**目标：明确 全部导入 和 按需导入 的区别**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173124265.png" alt="image-20250615173124265" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173131962.png" alt="image-20250615173131962" style="zoom:50%;" />



**目标：阅读文档，掌握 全部导入 的基本使用**



**官网：**vant-ui([Vant 2 - 轻量、可靠的移动端组件库](https://vant-ui.github.io/vant/v2/#/zh-CN/))

**全部导入：**

① 安装 vant-ui

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173441411.png" alt="image-20250615173441411" style="zoom:50%;" />

② main.js 中注册

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173458087.png" alt="image-20250615173458087" style="zoom:50%;" />

③ 使用测试

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173509706.png" alt="image-20250615173509706" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173518610.png" alt="image-20250615173518610" style="zoom:50%;" />



**目标：阅读文档，掌握 按需导入 的基本使用**



**按需导入：**



① 安装 vant-ui (已安装)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173551547.png" alt="image-20250615173551547" style="zoom:50%;" />

② 安装插件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173603830.png" alt="image-20250615173603830" style="zoom:50%;" />

③ babel.config.js 中配置

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173616043.png" alt="image-20250615173616043" style="zoom:50%;" />

④ main.js 按需导入注册

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173627052.png" alt="image-20250615173627052" style="zoom:50%;" />

⑤ 测试使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173636804.png" alt="image-20250615173636804" style="zoom:50%;" />

⑥ 提取到 vant-ui.js 中，main.js 导入

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173648006.png" alt="image-20250615173648006" style="zoom:50%;" />



## 7. 项目中的 vw 适配



**目标：**基于 postcss 插件 实现项目 vw 适配

[Vant 2 - 轻量、可靠的移动端组件库](https://vant-ui.github.io/vant/v2/#/zh-CN/advanced-usage)

① 安装插件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173739548.png" alt="image-20250615173739548" style="zoom:50%;" />

② 根目录新建 postcss.config.js 文件，填入配置

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173809977.png" alt="image-20250615173809977" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173818363.png" alt="image-20250615173818363" style="zoom:50%;" />



## 8. 路由设计配置



**目标：分析项目页面，设计路由，配置一级路由**



但凡是单个页面，独立展示的，都是一级路由

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173906455.png" alt="image-20250615173906455" style="zoom:50%;" />



**目标：阅读vant组件库文档，实现<font color='red'>底部导航 tabbar</font>**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173932135.png" alt="image-20250615173932135" style="zoom:50%;" />

**tabbar标签页：**

① vant-ui.js 按需引入

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615173953044.png" alt="image-20250615173953044" style="zoom:50%;" />

② layout.vue 粘贴官方代码测试			<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174003746.png" alt="image-20250615174003746" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174018047.png" alt="image-20250615174018047" style="zoom:50%;" />

③ 修改文字、图标、颜色

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174030943.png" alt="image-20250615174030943" style="zoom:50%;" />



**目标：基于底部导航，完成二级路由配置**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174056147.png" alt="image-20250615174056147" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174107014.png" alt="image-20250615174107014" style="zoom:50%;" />



## 9. 登录页静态布局



**目标：**基于笔记，快速实现登录页静态布局

准备工作

1. 新建 <font color='red'>styles/common.less</font> 重置默认样式
2. main.js 导入 common.less
3. 图片素材拷贝到 assets 目录【备用】

登录页静态布局编写

1.  <font color='red'>头部组件</font>说明 (NavBar)
2.  通用样式覆盖
3.  其他静态结构编写

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174810568.png" alt="image-20250615174810568" style="zoom:50%;" />



## 10. request模块 - axios 封装



**目标：**将 axios 请求方法，封装到 request 模块

使用 axios 来<font color='red'>请求后端接口</font>, 一般都会对 axios 进行 <font color='red'>一些配置</font> (比如: 配置基础地址，请求响应拦截器等)

所以项目开发中, 都会对 axios 进行基本的<font color='red'>二次封装</font>, 单独封装到一个 request 模块中, <font color='red'>便于维护使用</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615174908574.png" alt="image-20250615174908574" style="zoom:50%;" />

**接口文档地址：**

[wiki - 智慧商城-实战项目](https://apifox.com/apidoc/shared/12ab6b18-adc2-444c-ad11-0e60f5693f66/doc-2221080)

**基地址：**

http://cba.itlike.com/public/index.php?s=/api/



## 11. 图形验证码功能完成



**目标：**基于请求回来的 base64 图片，实现图形验证码功能

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175031684.png" alt="image-20250615175031684" style="zoom:50%;" />

**说明：**

1. 图形验证码，本质就是一个<font color='red'>请求回来的图片</font>
2. 用户将来输入图形验证码，用于强制人机交互，可以<font color='red'>抵御机器自动化攻击</font> (例如：避免批量请求获取短信)
需求：
1. 动态将请求回来的 base64 图片，解析渲染出来
2. 点击验证码图片盒子，要刷新验证码

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175039115.png" alt="image-20250615175039115" style="zoom:50%;" />



## 12. api 接口模块 -封装图片验证码接口



**目标：**将请求封装成方法，统一存放到 api 模块，与页面分离

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175114606.png" alt="image-20250615175114606" style="zoom:50%;" />

**以前的模式：**

1. 页面中充斥着请求代码，可阅读性不高
2. 相同的请求没有复用
3. 请求没有统一管理

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175131137.png" alt="image-20250615175131137" style="zoom:50%;" />

**封装api模块的好处：**

1. 请求与页面逻辑分离
2. 相同的请求可以直接复用
3. 请求进行了统一管理

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175144341.png" alt="image-20250615175144341" style="zoom:50%;" />



## 13. Toast 轻提示



**目标：**阅读文档，掌握 toast 轻提示

**注册安装：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175612337.png" alt="image-20250615175612337" style="zoom:50%;" />

**两种使用方式**

① 导入调用 (组件内 或 非组件中均可)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175629860.png" alt="image-20250615175629860" style="zoom:50%;" />

② 通过this直接调用 (必须组件内) 

**本质：**将方法，注册挂载到了Vue原型上 <font color='red'>Vue.prototype.$toast = xxx</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175741346.png" alt="image-20250615175741346" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175750060.png" alt="image-20250615175750060" style="zoom:50%;" />



## 14. 短信验证倒计时



**目标：**实现短信验证倒计时功能

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175829274.png" alt="image-20250615175829274" style="zoom:50%;" />

步骤分析：
1. 点击按钮，实现 <font color='red'>倒计时</font> 效果
2. 倒计时之前的 <font color='red'>校验处理</font> (手机号、验证码)
3. 封装<font color='red'>短信验证请求接口</font>，发送请求添加提示

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615175851289.png" alt="image-20250615175851289" style="zoom:50%;" />



## 15. 登录功能



**目标：**封装api登录接口，实现登录功能

**步骤分析：**

1. 阅读接口文档，<font color='red'>封装登录接口</font>
2. 登录前的校验 (<font color='red'>手机号</font>，图形验证码，<font color='red'>短信验证码</font>)
3. <font color='red'>调用方法</font>，发送请求，成功添加提示并跳转

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615180057905.png" alt="image-20250615180057905" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615180105496.png" alt="image-20250615180105496" style="zoom:50%;" />



## 16. 响应拦截器统一处理错误提示



**目标：**通过响应拦截器，统一处理接口的错误提示

**问题：**每次请求，都会有可能会错误，就都需要错误提示

**说明：**响应拦截器是咱们拿到数据的 第一个 数据流转站，可以在里面<font color='red'>统一处理错误</font>。**只要不是 200, 就给默认提示，抛出错误**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191220160.png" alt="image-20250615191220160" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191227175.png" alt="image-20250615191227175" style="zoom:50%;" />



## 17. 登录权证信息存储



**目标：**vuex 构建 user 模块存储登录权证 (token & userId)

**补充说明：**

1. token 存入 vuex 的好处，<font color='red'>易获取，响应式</font>
2. vuex 需要分模块 => user 模块

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191318183.png" alt="image-20250615191318183" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191325881.png" alt="image-20250615191325881" style="zoom:50%;" />



## 18. storage存储模块 - vuex 持久化处理



**目标：**封装 storage 存储模块，利用本地存储，进行 vuex 持久化处理

问题1：vuex 刷新会丢失，怎么办？

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191407716.png" alt="image-20250615191407716" style="zoom:50%;" />

问题2：每次存取操作太长，太麻烦？

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191422599.png" alt="image-20250615191422599" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191430600.png" alt="image-20250615191430600" style="zoom:50%;" />



## 19. 添加请求 loading 效果



**目标：**统一在每次请求后台时，添加 loading 效果

**背景：**有时候因为网络原因，一次请求的结果可能需要一段时间后才能回来，此时，需要给用户<font color='red'> 添加 loading 提示</font>。

**添加 loading 提示的好处：**

1. 节流处理：防止用户在一次请求还没回来之前，多次进行点击，发送无效请求
2. 友好提示：告知用户，目前是在加载中，请耐心等待，用户体验会更好

**实操步骤：**

1. <font color='red'>请求拦截器</font>中，每次请求，<font color='red'>打开 loading</font>
2. <font color='red'>响应拦截器</font>中，每次响应，<font color='red'>关闭 loading</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191548436.png" alt="image-20250615191548436" style="zoom:50%;" />



## 20. 页面访问拦截



**目标：**基于全局前置守卫，进行页面访问拦截处理

**说明：**智慧商城项目，大部分页面，<font color='red'>游客都可以直接访问</font>, 如遇到需要登录才能进行的操作，提示并跳转到登录

**但是：**对于支付页，订单页等，必须是登录的用户才能访问的，游客不能进入该页面，<font color='red'>需要做拦截处理</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191646094.png" alt="image-20250615191646094" style="zoom:50%;" />

路由导航守卫 - 全局前置守卫([导航守卫 | Vue Router](https://v3.router.vuejs.org/zh/guide/advanced/navigation-guards.html#全局前置守卫))
1. 所有的路由一旦被匹配到，都会先经过全局前置守卫

2. 只有全局前置守卫放行，才会真正解析渲染组件，才能看到页面内容

访问权限页面时，拦截或放行的关键点？ → <font color='red'>用户是否有登录权证 token</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191740456.png" alt="image-20250615191740456" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191748337.png" alt="image-20250615191748337" style="zoom:50%;" />



## 21. 首页 - 静态结构准备 & 动态渲染



**目标：**实现首页静态结构，封装接口，完成首页动态渲染

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191835672.png" alt="image-20250615191835672" style="zoom:50%;" />



## 22. 搜索 - 历史记录管理



**目标：**构建搜索页的静态布局，完成历史记录的管理

**需求：**

1. 搜索历史基本渲染
2. 点击搜索 (添加历史) 
  -  点击 搜索按钮 或 底下历史记录，都能进行搜索
  -  ① 若之前 <font color='red'>没有</font> 相同搜索关键字，则直接<font color='red'>追加到最前面</font>
  -  ② 若之前 <font color='red'>已有</font> 相同搜索关键字，将该<font color='red'>原有关键字移除，再追加</font>
3. 清空历史：添加清空图标，可以清空历史记录
4. 持久化：搜索历史需要持久化，刷新历史不丢失

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615191943802.png" alt="image-20250615191943802" style="zoom:50%;" />



## 23. 搜索列表 - 静态布局 & 动态渲染



**目标：**实现搜索列表页静态结构，封装接口，完成搜索列表页的渲染

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192014311.png" alt="image-20250615192014311" style="zoom:50%;" />



## 24. 商品详情- 静态布局 & 渲染



**目标：**实现商品详情静态结构，封装接口，完成商品详情页渲染

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192040856.png" alt="image-20250615192040856" style="zoom:50%;" />



## 25. 加入购物车 



### 25.1 唤起弹层



**目标：**点击加入购物车，唤起弹层效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192105060.png" alt="image-20250615192105060" style="zoom:50%;" />



### 25.2 封装数字框组件



**目标：**封装弹层中的数字框组件

**分析：**组件名 CountBox

1. 静态结构，左中右三部分
2. 数字框的数字，应该是外部传递进来的 (<font color='red'>父传子</font>)
3. 点击 + - 号，可以修改数字 (<font color='red'>子传父</font>)
4. 使用 <font color='red'>v-model</font> 实现封装 (:value 和 @input 的简写)
5. 数字不能减到小于 1
6. 可以直接输入内容，输入完成判断是否合法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192220054.png" alt="image-20250615192220054" style="zoom:50%;" />



### 25.3 判断 token 添加登录提示



**目标：**给未登录的用户，添加登录提示

**说明：**加入购物车，是一个 <font color='red'>登录后的用户</font> 才能进行的操作

所以需要进行鉴权判断，判断用户 token 是否存在

1. 若存在：继续加入购物车操作
2. 不存在：<font color='red'>提示</font> 用户未登录，引导到登录页，<font color='red'>登录完回跳</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192319232.png" alt="image-20250615192319232" style="zoom:50%;" />



### 25.4 封装接口进行请求



**目标：**封装接口，进行加入购物车的请求

1. api/cart.js 中封装接口
2. 页面中调用接口
3. 遇到问题：接口需要传递 token
4. 解决问题：请求拦截器统一携带 token
5. 小图标定制

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192453601.png" alt="image-20250615192453601" style="zoom:50%;" />



## 26. 购物车模块



**说明：**购物车 <font color='red'>数据联动关系</font> 较多，且通常会封装一些 <font color='red'>小组件</font>，所以为了便于维护，一般都会将购物车的数据基于 vuex <font color='red'>分模块管理</font>

**需求分析：**

1. 基本静态结构 (快速实现)
2. 构建 vuex <font color='red'>cart 模块</font>，获取数据存储
3. 基于 数据 <font color='red'>动态渲染</font> 购物车列表
4. 封装 <font color='red'>getters</font> 实现动态统计
5. 全选反选功能
6. 数字框修改数量功能
7. 编辑切换状态，删除功能
8. 空购物车处理

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192613945.png" alt="image-20250615192613945" style="zoom:50%;" />



## 27. 订单结算台



**说明：**所有的结算，本质上就是 <font color='red'>跳转到 "订单结算台"</font>，并且，跳转的同时，需要<font color='red'> 携带上对应的订单相关参数</font>，具体需要哪些参数，基于 "订单结算台" 的需求来定。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615192659073.png" alt="image-20250615192659073" style="zoom:50%;" />



### 27.1 确认订单信息



**目标：**封装通用的订单信息确认接口

**说明：**这里的订单信息确认结算，有两种情况

1. 购物车结算
2. 立即购买结算

订单信息确认，可以共用同一个接口(参数不同)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193024151.png" alt="image-20250615193024151" style="zoom:50%;" />



### 27.2 购物车结算



**目标：**购物车结算跳转，<font color='red'>传递参数</font>，调用接口渲染订单结算台

**核心步骤：**

1. 跳转传递查询参数 mode="cart" 和 cartIds
2. 页面中 $route.query 接收参数
3. 调用接口，获取数据
4. 基于数据渲染

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193112079.png" alt="image-20250615193112079" style="zoom:50%;" />



### 27.3 立即购买结算



**目标：**购物车结算跳转，<font color='red'>传递参数</font>，调用接口渲染订单结算台

核心步骤：

1. 跳转传递查询参数 

  mode="buyNow", goodsId, goodsSkuId, goodsNum

2. 页面中 $route.query 接收参数

3. 调用接口，获取数据

4. 基于数据渲染

5. 未登录时，确认框的复用 (<font color='red'>mixins混入</font>)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193342591.png" alt="image-20250615193342591" style="zoom:50%;" />



## 28. 提交订单并支付



**目标：**封装 API 请求方法，提交订单并支付

**核心步骤：**

1. 封装通用请求方法
2. 买家留言绑定
3. 注册事件，调用方法提交订单并支付

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193600320.png" alt="image-20250615193600320" style="zoom:50%;" />

### mixin



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250618100059240.png" alt="image-20250618100059240" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250618100124930.png" alt="image-20250618100124930" style="zoom:50%;" />

## 29. 订单管理 & 个人中心 (快速实现)



**目标：**基于笔记，快速实现 订单管理 和 个人中心 跑通流程

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193632726.png" alt="image-20250615193632726" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193701235.png" alt="image-20250615193701235" style="zoom:50%;" />



## 30. 打包发布



**目标：明确打包的作用**



**说明：**vue脚手架只是开发过程中，协助开发的工具，当真正开发完了 => 脚手架不参与上线

**打包的作用：**

① 将多个文件压缩合并成一个文件
② 语法降级
③ less sass ts 语法解析
④ ....

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193846389.png" alt="image-20250615193846389" style="zoom:50%;" />

打包后，可以生成，浏览器能够直接运行的网页 => 就是需要上线的源码！



**目标：打包的命令 和 配置**



**说明：**vue脚手架工具已经提供了打包命令，直接使用即可。

**命令：**yarn build

**结果：**在项目的根目录会自动创建一个文件夹 <font color='red'>dist</font> , dist 中的文件就是打包后的文件，只需要放到服务器中即可。

**配置：**默认情况下，需要放到服务器根目录打开，如果希望双击运行，需要配置publicPath 配成相对路径

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615193951081.png" alt="image-20250615193951081" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615194003176.png" alt="image-20250615194003176" style="zoom:50%;" />



## 31. 打包优化：路由懒加载



**目标：**配置路由懒加载，实现打包优化

**说明：**当打包构建应用时，JavaScript 包会变得非常大，影响页面加载。如果我们能把不同路由对应的组件分割成不同的代码块，然后当路由<font color='red'>被访问的时候才加载对应组件</font>，这样就更加<font color='red'>高效</font>了。

[路由懒加载 | Vue Router](https://router.vuejs.org/zh/guide/advanced/lazy-loading.html)

步骤1： 异步组件改造

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615194158473.png" alt="image-20250615194158473" style="zoom:50%;" />

步骤2： 路由中应用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250615194209398.png" alt="image-20250615194209398" style="zoom:50%;" />



# ***Vue 3***



# 十六、Vue 3



## 1. 为什么要学 Vue3



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200148055.png" alt="image-20250621200148055" style="zoom:50%;" />



### 1.1 Vue3的优势



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200213372.png" alt="image-20250621200213372" style="zoom:50%;" />



### 1.2 Vue2 选项式 API vs Vue3 组合式API



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200242258.png" alt="image-20250621200242258" style="zoom:50%;" />

**需求：**点击按钮，让数字 +1

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200301389.png" alt="image-20250621200301389" style="zoom:50%;" />



## 2. create-vue搭建Vue3项目



### 2.1 认识 create-vue



create-vue是Vue<font color='red'>官方新的脚手架工具</font>，底层切换到了 <font color='red'>vite（下一代构建工具）</font>，为开发提供极速响应

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200522797.png" alt="image-20250621200522797" style="zoom:50%;" />



### 2.2 使用create-vue创建项目



1. 前提环境条件

  <font color='red'>已安装 16.0 或更高版本的 Node.js</font>
  node -v

2. 创建一个Vue应用

  <font color='red'>npm init vue@latest</font>
  这一指令将会安装并执行 create-vue

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200613792.png" alt="image-20250621200613792" style="zoom:50%;" />



## 3. 熟悉项目目录和关键文件



### 3.1 项目目录和关键文件



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200655463.png" alt="image-20250621200655463" style="zoom:50%;" />

**关键文件：**

1. vite.config.js - 项目的配置文件 <font color='red'>基于vite的配置</font>
2. package.json - 项目包文件 <font color='red'>核心依赖项变成了 Vue3.x 和 vite</font>
3. main.js - 入口文件 <font color='red'>createApp函数创建应用实例</font>
4. app.vue - 根组件 <font color='red'>SFC单文件组件 script - template - style</font>
变化一：脚本script和模板template顺序调整
变化二：模板template不再要求唯一根元素
变化三：脚本script添加setup标识支持组合式API
5. index.html - 单页入口 <font color='red'>提供id为app的挂载点</font>



## 4. 组合式API - setup选项



### 4.1 setup选项的写法和执行时机



1. 执行时机，比 beforeCreate 还要早
2. setup 函数中，获取不到this （this 是 undefined)，因为 setup 创建时机很早，导致组件实例还没有被创建出来，所以没有this

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200756315.png" alt="image-20250621200756315" style="zoom:50%;" />



### 4.2 setup选项中写代码的特点



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200816426.png" alt="image-20250621200816426" style="zoom:50%;" />



### 4.3 `<script setup>` 语法糖



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200902286.png" alt="image-20250621200902286" style="zoom:50%;" />



### 4.4 `<script setup>` 语法糖原理



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621200924768.png" alt="image-20250621200924768" style="zoom:50%;" />



> [!TIP]
>
> 1. setup选项的执行时机？
>
> 	  <font color='red'>beforeCreate钩子之前 自动执行</font>
>
> 2. setup写代码的特点是什么？
>
> 	  <font color='red'>定义数据 + 函数 然后以对象方式return</font>
>
> 3. `<script setup>`解决了什么问题？
>
> 	  <font color='red'>经过语法糖的封装更简单的使用组合式API</font>
>
> 4. setup中的this还指向组件实例吗？
>
> 	  <font color='red'>指向undefined</font>
>



## 5. 组合式API - reactive和ref函数



### 5.1 reactive()



**作用：**接受<font color='red'>**对象**类型数据的参数传入</font>并返回一个<font color='red'>响应式的对象</font>

**核心步骤：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621201704176.png" alt="image-20250621201704176" style="zoom:50%;" />

1. 从 vue 包中<font color='red'>导入 reactive 函数</font>
2. 在 `<script setup>` 中<font color='red'>执行 reactive 函数</font>并传入<font color='red'>类型为对象</font>的初始值，并使用变量接收返回值



### 5.2 ref()



**作用：**接收<font color='red'>简单类型或者对象类型的数据</font>传入并返回一个<font color='red'>响应式的对象</font>

**核心步骤：**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621201813023.png" alt="image-20250621201813023" style="zoom:50%;" />

1. 从 vue 包中<font color='red'>导入 ref 函数</font>
2. 在 `<script setup>` 中<font color='red'>执行 ref 函数</font>并传入初始值，使用<font color='red'>变量接收 </font>ref 函数的返回值



> [!TIP]
>
> 1. reactive和ref函数的共同作用是什么 ？
>
>   ​	<font color='red'>用函数调用的方式生成响应式数据</font>
>
> 2. reactive vs ref ？
>
> 	<font color='red'>	1.reactive不能处理简单类型的数据</font>
>
> 	<font color='red'>	2.ref参数类型支持更好但是必须通过.value访问修改</font>
>
> 	​	3.ref函数的内部实现依赖于reactive函数
>
> 3. 在实际工作中推荐使用哪个？
>
>   ​	<font color='red'>推荐使用ref函数，更加灵活统一</font>



## 6. 组合式API - computed



### 6.1 computed计算属性函数



计算属性基本思想和Vue2的完全一致，组合式API下的计算属性<font color='red'>只是修改了写法</font>

**核心步骤：**

1. <font color='red'>导入</font>computed函数

2. <font color='red'>执行函数</font> 在回调参数中<font color='red'>return基于响应式数据做计算的值</font>，用<font color='red'>变量接收</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621221950285.png" alt="image-20250621221950285" style="zoom:50%;" />



**计算属性小案例**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202126596.png" alt="image-20250621202126596" style="zoom:50%;" />

<font color='red'>计算公式</font>：始终从原始响应式数组中筛选出大于2的所有项 - filter



> [!TIP]
>
> 最佳实践
> 1. 计算属性中不应该有“副作用”
>
>   ​	<font color='red'>比如异步请求/修改dom</font>
>
> 2. 避免直接修改计算属性的值
>
>   <font color='red'>	计算属性应该是只读的，特殊情况可以配置 get set</font>



## 7. 组合式API - watch



### 7.1 watch函数



**作用:** 侦听<font color='red'>一个或者多个数据</font>的变化，数据变化时执行回调函数

俩个额外参数：1. immediate（立即执行） 2. deep（深度侦听）



### 7.2 基础使用 - 侦听单个数据



1. <font color='red'>导入watch</font>函数
2. <font color='red'>执行watch函数</font>传入要侦听的响应式数据<font color='red'>(ref对象)</font>和回调函数

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202334206.png" alt="image-20250621202334206" style="zoom:50%;" />

**说明：**同时侦听多个响应式数据的变化，<font color='red'>不管哪个数据变化都需要执行回调</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202356923.png" alt="image-20250621202356923" style="zoom:50%;" />



### 7.3 immediate



**说明：**在侦听器创建时<font color='red'>立即触发回调</font>, 响应式数据变化之后继续执行回调

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202428704.png" alt="image-20250621202428704" style="zoom:50%;" />



### 7.4 deep



**默认机制：**通过watch监听的ref对象默认是<font color='red'>浅层侦听的，直接修改嵌套的对象属性不会触发回调执行</font>，需要开启deep选项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202510030.png" alt="image-20250621202510030" style="zoom:50%;" />



### 7.5 精确侦听对象的某个属性



**需求：**在不开启deep的前提下，侦听age的变化，只有age变化时才执行回调



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621202537282.png" alt="image-20250621202537282" style="zoom:50%;" />



> [!TIP]
>
> 1. 作为watch函数的第一个参数，ref对象需要添加.value吗？
>
>   ​	<font color='red'>不需要，第一个参数就是传 ref 对象</font>
>
> 2. watch只能侦听单个数据吗？
>
>   ​	<font color='red'>单个 或者 多个</font>
>
> 3. 不开启deep，直接监视 复杂类型，修改属性 能触发回调吗？
>
>   ​	<font color='red'>不能，默认是浅层侦听</font>
>
> 4. 不开启deep，精确侦听对象的某个属性？
>
>   ​	<font color='red'>可以把第一个参数写成函数的写法，返回要监听的具体属性</font>





## 8. 组合式API - 生命周期函数



### 8.1 Vue3的生命周期API （选项式 VS 组合式）



|                   选项式API                   |                组合式API                 |
| :-------------------------------------------: | :--------------------------------------: |
| <font color='red'>beforeCreate/created</font> |      <font color='red'>setup</font>      |
|                  beforeMount                  |              onBeforeMount               |
|                    mounted                    |                onMounted                 |
|                 beforeUpdate                  |              onBeforeUpdate              |
|                    updated                    |                onUpdated                 |
|    <font color='red'>beforeUnmount</font>     | <font color='red'>onBeforeUnmount</font> |
|      <font color='red'>unmounted</font>       |   <font color='red'>onUnmounted</font>   |



### 8.2 生命周期函数基本使用



1. 导入生命周期函数
2. 执行生命周期函数 传入回调

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203323624.png" alt="image-20250621203323624" style="zoom:50%;" />



### 8.3 执行多次



生命周期函数是可以执行多次的，多次执行时传入的回调会在<font color='red'>时机成熟时依次执行</font>



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203347686.png" alt="image-20250621203347686" style="zoom:50%;" />



> [!TIP]
>
> 1. 组合式API中生命周期函数的格式是什么？
>
>   ​	<font color='red'>on + 生命周期名字</font>
>
> 2. 组合式API中可以使用onCreated吗？
>
>   ​	<font color='red'>没有这个钩子函数，直接写到setup中</font>
>
> 3. 组合式API中组件卸载完毕时执行哪个函数？
>
>   ​	<font color='red'>onUnmounted</font>



## 9. 组合式API - 父子通信



### 9.1 组合式API下的父传子



基本思想
1. 父组件中给<font color='red'>子组件绑定属性</font>
2. 子组件内部通过<font color='red'>props选项接收</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203514489.png" alt="image-20250621203514489" style="zoom:50%;" />



**defineProps 原理：**就是编译阶段的一个标识，实际编译器解析时，遇到后会进行编译转换

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203534727.png" alt="image-20250621203534727" style="zoom:50%;" />



### 9.2 组合式API下的子传父



**基本思想**

1. 父组件中给<font color='red'>子组件标签通过@绑定事件</font>
2. 子组件内部通过<font color='red'> emit 方法触发事件</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203630557.png" alt="image-20250621203630557" style="zoom:50%;" />



> [!TIP]
>
> 父传子
> 1. 父传子的过程中通过什么方式接收props？
>
>   ​	<font color='red'>defineProps( { 属性名：类型 } )</font>
>
> 2. setup语法糖中如何使用父组件传过来的数据？
>
>   ​	<font color='red'>const props = defineProps( { 属性名：类型 } )</font>
>   ​	<font color='red'>props.xxx</font>
>
> 子传父
>
> 1. 子传父的过程中通过什么方式得到emit方法？
>
>   ​	<font color='red'>defineEmits( [‘事件名称’] )</font>
>
> 2. 怎么触发事件
>
>   ​	<font color='red'>emit('自定义事件名', 参数)</font>



## 10. 组合式API - 模版引用



### 10.1 模板引用的概念



通过<font color='red'>ref标识</font>获取真实的<font color='red'>dom对象或者组件实例对象</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203837346.png" alt="image-20250621203837346" style="zoom:50%;" />



### 10.2 如何使用（以获取dom为例 组件同理）



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203858344.png" alt="image-20250621203858344" style="zoom:50%;" />

1. 调用ref函数生成一个ref对象
2. 通过ref标识绑定ref对象到标签



### 10.3 defineExpose()



默认情况下在`<script setup>`语法糖下<font color='red'>组件内部的属性和方法是不开放</font>给父组件访问的，可以通过defineExpose编译宏<font color='red'>指定哪些属性和方法允许访问</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621203956116.png" alt="image-20250621203956116" style="zoom:50%;" />



> [!TIP]
>
> 1. 获取模板引用的时机是什么？
>
>   ​	<font color='red'>组件挂载完毕</font>
>
> 2. defineExpose编译宏的作用是什么？
>
>   ​	<font color='red'>显式暴露组件内部的属性和方法</font>



## 11. 组合式API - provide和inject



### 11.1 作用和场景



顶层组件向任意的底层组件<font color='red'>传递数据和方法</font>，实现<font color='red'>跨层组件通信</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204113128.png" alt="image-20250621204113128" style="zoom:50%;" />



### 11.2 跨层传递普通数据



1. 顶层组件通过<font color='red'>provide函数提供</font>数据
2. 底层组件通过<font color='red'>inject函数获取</font>数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204210273.png" alt="image-20250621204210273" style="zoom:50%;" />



### 11.3 跨层传递响应式数据



在调用provide函数时，第二个参数设置为<font color='red'>ref对象</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204237168.png" alt="image-20250621204237168" style="zoom:50%;" />



### 11.4 跨层传递方法



顶层组件可以向底层组件传递方法，<font color='red'>底层组件调用方法修改顶层组件中的数据</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204313904.png" alt="image-20250621204313904" style="zoom:50%;" />



### 11.5 需求解决思考



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204337354.png" alt="image-20250621204337354" style="zoom:50%;" />



> [!TIP]
>
> 1. provide和inject的作用是什么？
>
>   ​	<font color='red'>跨层组件通信</font>
>
> 2. 如何在传递的过程中保持数据响应式？
>
>   ​	<font color='red'>第二个参数传递ref对象</font>
>
> 3. 底层组件想要通知顶层组件做修改，如何做？
>
>   ​	<font color='red'>传递方法，底层组件调用方法</font>
>
> 4. 一颗组件树中只有一个顶层或底层组件吗？
>
>   ​	<font color='red'>相对概念，存在多个顶层和底层的关系</font>



## 12. Vue3.3新特性-defineOptions





**背景说明：**

有 <font color='red'>`<script setup>`</font> 之前，如果要定义 props, emits 可以轻而易举地添加一个与 setup 平级的属性。
但是用了 <font color='red'><script setup></font> 后，就没法这么干了 setup 属性已经没有了，自然无法添加与其平级的属性。

为了解决这一问题，引入了<font color='red'> defineProps</font> 与 <font color='red'>defineEmits </font>这两个宏。但这只解决了 <font color='red'>props </font>与<font color='red'> emits </font>这两个属性。
如果我们要定义组件的 name 或其他自定义的属性，还是得回到最原始的用法——再添加一个普通的 <script> 标签。
这样就会存在两个 <script> 标签。让人无法接受

所以在 Vue 3.3 中新引入了<font color='red'> defineOptions</font> 宏。顾名思义，主要是用来定义 <font color='red'>Options API</font> 的选项。可以用
defineOptions 定义任意的选项， props, emits, expose, slots 除外（因为这些可以使用 defineXXX 来做到）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204639424.png" alt="image-20250621204639424" style="zoom:50%;" />



## 13. Vue3.3新特性-defineModel



**Vue3 中的 v-model 和 defineModel**



在Vue3中，自定义组件上使用v-model, 相当于传递一个modelValue属性，同时触发 update:modelValue 事件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204742599.png" alt="image-20250621204742599" style="zoom:50%;" />

我们需要先定义 props，再定义 emits 。其中有许多重复的代码。如果需要修改此值，还需要手动调用 emit 函数。

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250621204753740.png" alt="image-20250621204753740" style="zoom:50%;" />



# 十七、Pinia 快速入门





## 1. 什么是Pinia



Pinia 是 Vue 的最新 <font color='red'>状态管理工具</font> ，是 Vuex 的 <font color='red'>替代品</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222303792.png" alt="image-20250622222303792" style="zoom:50%;" />

1. 提供更加简单的API （去掉了 mutation ）
2. 提供符合，组合式风格的API （和 Vue3 新语法统一）
3. 去掉了 modules 的概念，每一个 store 都是一个独立的模块
4. 配合 TypeScript 更加友好，提供可靠的类型推断



## 2. 手动添加Pinia到Vue项目



在实际开发项目的时候，关于Pinia的配置，可以在项目创建时自动添加

现在我们初次学习，从零开始：

1. 使用 Vite 创建一个空的 Vue3 项目
npm create vue@latest
2. <font color='red'>按照官方文档</font> 安装 pinia 到项目中

![image-20250623103114260](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250623103114260.png)

> 以上代码在 main.js 中

## 3. Pinia基础使用 - 计数器案例



1. 定义store
2. 组件使用store

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222404002.png" alt="image-20250622222404002" style="zoom:50%;" />



## 4. getters实现



Pinia中的 getters 直接使用 <font color='red'>computed函数</font> 进行模拟, 组件中需要使用<font color='red'>需要把 getters return出去</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222439956.png" alt="image-20250622222439956" style="zoom:50%;" />



## 5. action异步实现



**编写方式：**异步action函数的写法和<font color='red'>组件中获取异步数据的写法完全一致</font>

**接口地址：**http://geek.itheima.net/v1_0/channels

**需求：**在Pinia中获取频道列表数据并把数据渲染App组件的模板中

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222517098.png" alt="image-20250622222517098" style="zoom:50%;" />



## 6. storeToRefs工具函数



使用storeToRefs函数可以辅助保持数据<font color='red'>（state + getter）</font>的响应式解构

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222542350.png" alt="image-20250622222542350" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222553255.png" alt="image-20250622222553255" style="zoom:50%;" />



## 7. Pinia的调试



Vue官方的 <font color='red'>dev-tools 调试工具</font> 对 Pinia直接支持，可以直接进行调试

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222624114.png" alt="image-20250622222624114" style="zoom: 50%;" />



## 8. Pinia持久化插件



官方文档：https://prazdevs.github.io/pinia-plugin-persistedstate/zh/

1. 安装插件 pinia-plugin-persistedstate

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222814235.png" alt="image-20250622222814235" style="zoom:50%;" />

2. main.js 使用

  <img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622222825648.png" alt="image-20250622222825648" style="zoom:50%;" />

3. store仓库中，<font color='red'>persist: true</font> 开启

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250624152723661.png" alt="image-20250624152723661" style="zoom:50%;" />



> [!TIP]
>
> 1. Pinia是用来做什么的？
>
>   <font color='red'>新一代的状态管理工具，替代vuex</font>
>
> 2. Pinia中还需要mutation吗？
>
>   <font color='red'>不需要，action 既支持同步也支持异步</font>
>
> 3. Pinia如何实现getter？
>
>   <font color='red'>computed计算属性函数</font>
>
> 4. Pinia产生的Store如何解构赋值数据保持响应式？
>
>   <font color='red'>storeToRefs</font>
>
> 5. Pinia 如何快速实现持久化？
>
>   <font color='red'>pinia-plugin-persistedstate</font>



# Vue3 大事件管理系统





## 1. 大事件项目介绍 和 创建



### 1.1 Vue3 大事件管理系统



**在线演示：** https://fe-bigevent-web.itheima.net/login

**接口文档:** https://apifox.com/apidoc/shared-26c67aee-0233-4d23-aab7-08448fdf95ff/api-93850835

**基地址：** http://big-event-vue-api-t.itheima.net

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223025829.png" alt="image-20250622223025829" style="zoom:50%;" />



### 1.2 pnpm 包管理器 - 创建项目



**一些优势：**比同类工具快2倍左右、节省磁盘空间... https://www.pnpm.cn/

**安装方式：**npm install -g pnpm

**创建项目：**pnpm create vue

|         npm          |       yarn        |                    pnpm                    |
| :------------------: | :---------------: | :----------------------------------------: |
|     npm install      |       yarn        |   <font color='red'>pnpm install</font>    |
|  npm install axios   |  yarn add axios   |  <font color='red'>pnpm add axios</font>   |
| npm install axios -D | yarn add axios -D | <font color='red'>pnpm add axios -D</font> |
| npm uninstall axios  | yarn remove axios | <font color='red'>pnpm remove axios</font> |
|     npm run dev      |     yarn dev      |     <font color='red'>pnpm dev</font>      |



### 1.3 创建项目



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223327160.png" alt="image-20250622223327160" style="zoom:50%;" />



## 2. Eslint 配置代码风格



配置文件 .eslintrc.cjs
1. prettier 风格配置 https://prettier.io
	- 单引号
	- 不使用分号
	- 宽度80字符
	- 不加对象|数组最后逗号
	- 换行符号不限制（win mac 不一致）
2. vue组件名称多单词组成（忽略index.vue）
3. props解构（关闭）

提示：安装Eslint且配置保存修复，不要开启默认的自动保存格式化

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223449141.png" alt="image-20250622223449141" style="zoom:50%;" />



## 3. 配置代码检查工作流



### 3.1 提交前做代码检查



1. 初始化 git 仓库，执行 <font color='red'>git init</font> 即可
2. 初始化 husky 工具配置，执行 <font color='red'>pnpm dlx husky-init && pnpm install</font> 即可
https://typicode.github.io/husky/
3. 修改 .husky/pre-commit 文件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223538139.png" alt="image-20250622223538139" style="zoom:50%;" />

问题：pnpm lint 是全量检查，<font color='red'>耗时</font>问题，<font color='red'>历史</font>问题



### 3.2 暂存区 eslint 校验



1. 安装 lint-staged 包 <font color='red'>pnpm i lint-staged -D</font>
2. package.json 配置 lint-staged 命令
3. .husky/pre-commit 文件修改

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223628633.png" alt="image-20250622223628633" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223616685.png" alt="image-20250622223616685" style="zoom:50%;" />



> [!TIP]
>
> 1. 如何在 git commit 前执行 eslint 检查？
>
>   <font color='red'>使用 husky 这个 git hooks 工具</font>
>
> 2. 如何只检查暂存区代码？
>
>   <font color='red'>使用 lint-staged 工具</font>



## 4. 目录调整



默认生成的目录结构不满足我们的开发需求，所以这里需要做一些自定义改动。

主要是以下工作:

1. 删除一些初始化的默认文件
2. 修改剩余代码内容
3. 新增调整我们需要的目录结构
4. 拷贝全局样式和图片，安装预处理器支持

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223730335.png" alt="image-20250622223730335" style="zoom:50%;" />



## 5. vue-router4 路由代码解析



### 5.1 路由初始化



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223757595.png" alt="image-20250622223757595" style="zoom:50%;" />

1. 创建路由实例由<font color='red'> createRouter</font> 实现
2. 路由模式

- history 模式使用 <font color='red'>createWebHistory()</font>               地址栏不带 #
- hash 模式使用<font color='red'> createWebHashHistory()</font>         地址栏带 #
- 参数是<font color='red'>基础路径</font>，默认/，可以在vite.confiig.js文件中配置base属性，以设置此参数的值

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250624145650869.png" alt="image-20250624145650869" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250624145707290.png" alt="image-20250624145707290" style="zoom:50%;" />

此属性的效果是恒定地在地址前面加上base属性的值

### 5.2 总结



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622223920694.png" alt="image-20250622223920694" style="zoom:50%;" />

创建一个路由实例，路由模式是history模式，路由的基础地址是 vite.config.js中的 base 配置的值，默认是 / , 环境变量地址： https://cn.vitejs.dev/guide/env-and-mode.html



## 6. 引入 Element Plus 组件库



**按需引入 Element Plus** 



1. 安装： <font color='red'>pnpm add element-plus</font>

2. 配置按需导入：

	官方文档： https://element-plus.org/zh-CN/guide/quickstart.html

3. 直接使用组件

4. 彩蛋：默认 <font color='red'>components</font> 下的文件也会被 <font color='red'>自动注册~</font>font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224206956.png" alt="image-20250622224206956" style="zoom:50%;" />



## 7. Pinia 构建仓库 和 持久化



![image-20250622224241341](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224241341.png)



## 8. Pinia 仓库统一管理



pinia 独立维护
- 现在：初始化代码在 <font color='red'>main.js</font> 中，仓库代码在 <font color='red'>stores </font>中，代码分散职能不单一
- 优化：由 <font color='red'>stores </font>统一维护，在 <font color='red'>stores/index.js</font> 中完成 <font color='red'>pinia</font> 初始化，交付 <font color='red'>main.js</font> 使用

仓库 统一导出

- 现在：使用一个仓库 <font color='red'>import { useUserStore } from `./stores/user.js` </font>不同仓库路径不一致
- 优化：由 <font color='red'>stores/index.js</font> 统一导出，导入路径统一 <font color='red'>`./stores`</font>，而且仓库维护在 <font color='red'>stores/modules</font> 中



## 9. 数据交互 - 请求工具设计



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224432480.png" alt="image-20250622224432480" style="zoom:50%;" />



## 10. 整体路由设计



**首页整体路由设计**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224523288.png" alt="image-20250622224523288" style="zoom:50%;" />



## 11. 具体业务功能实现



### 11.1 登录注册页面 [element-plus 表单 & 表单校验]



功能需求说明：
1. 注册登录 静态结构 & 基本切换
2. 注册功能 (校验 + 注册)
3. 登录功能 (校验 + 登录 + 存token)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224600655.png" alt="image-20250622224600655" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250624201526651.png" alt="image-20250624201526651" style="zoom:50%;" />



### 11.2 首页 layout 架子 [element-plus 菜单组件]



功能需求说明：
1. 基本架子拆解 (菜单组件的使用)
2. 登录访问拦截
3. 用户基本信息获取&渲染
4. 退出功能 [element-plus 确认框]

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224626512.png" alt="image-20250622224626512" style="zoom:50%;" />



### 11.3 文章分类页面 - [element-plus 表格]



功能需求说明：
1. 基本架子 - PageContainer 封装
2. 文章分类渲染 & loading 处理
3. 文章分类添加编辑 [element-plus 弹层]
4. 文章分类删除

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250622224649711.png" alt="image-20250622224649711" style="zoom:50%;" />
