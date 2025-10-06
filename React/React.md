#  1. React介绍



**React是什么**

React由Meta公司研发，是一个用于 <font color='red'>构建Web和原生交互界面的库</font>

![image-20250820135858250](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820135858250.png)



**React的优势**

相较于传统基于DOM开发的优势

![image-20250820135919460](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820135919460.png)

相较于其它前端框架的优势

![image-20250820135931107](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820135931107.png)



**React的市场情况**

全球最流行，大厂必备

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820140016287.png" alt="image-20250820140016287"  />

# 2. 开发环境搭建



**使用create-react-app快速搭建开发环境**



create-react-app是一个快速 创建React开发环境的工具，底层由Webpack构建，封装了配置细节，开箱即用

![image-20250820140140306](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820140140306.png)

执行命令：

```powershell
npx create-react-app react-basic
```

1. npx Node.js工具命令，查找并执行后续的包命令
2. create-react-app 核心包（固定写法），用于创建React项目
3. react-basic React项目的名称（可以自定义）

>  创建React项目的更多方式
> https://zh-hans.react.dev/learn/start-a-new-react-project

# 3. JSX基础



## 3.1 概念和本质



### 3.1.1 什么是JSX



**概念：**JSX是JavaScript和XML（HTML）的缩写，表示在<font color='red'>JS代码中编写HTML模版结构</font>,它是React中编写UI模版的方式

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820140549125.png" alt="image-20250820140549125"  />

**优势：**

1. HTML的声明式模版写法 2. JS的可编程能力



### 3.1.2 JSX的本质



JSX并不是标准的JS语法，它是<font color='red'>JS的语法扩展</font>，浏览器本身不能识别，需要通过<font color='red'>解析工具做解析</font>之后才能在浏览器中运行

![image-20250820140650469](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820140650469.png)



## 3.2 高频场景



### 3.2.1 JSX中使用JS表达式



在JSX中可以通过 <font color='red'>大括号语法{}</font> 识别 JavaScript中的表达式，比如常见的变量、函数调用、方法调用等等
1. 使用引号传递字符串
2. 使用JavaScript变量
3. 函数调用和方法调用
4. 使用JavaScript对象

<font color='red'>注意：</font>if语句、switch语句、变量声明属于语句，不是表达式，不能出现在{}中



### 3.2.2 JSX中实现列表渲染



![image-20250820141117506](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141117506.png)

**语法：**在JSX中可以使用原生JS中的map方法遍历渲染列表

![image-20250820141133644](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141133644.png)



### 3.2.3 JSX中实现条件渲染



![image-20250820141203568](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141203568.png)

**语法：**在React中，可以通过逻辑与运算符&&、三元表达式（?:）实现基础的条件渲染

![image-20250820141219546](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141219546.png)



### 3.2.4 JSX中实现复杂条件渲染



![image-20250820141242792](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141242792.png)

**需求：**列表中需要根据文章状态适配三种情况，单图，三图，和无图三种模式

**解决方案：**<font color='red'>自定义函数 + if判断语句</font>

# 4. React中的事件绑定



## 4.1 React 基础事件绑定



**语法：**on + 事件名称 = { 事件处理程序 }，整体上遵循驼峰命名法

![image-20250820141400989](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141400989.png)



## 4.2 使用事件对象参数



**语法：**在事件回调函数中设置形参e

![image-20250820141433987](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141433987.png)



## 4.3 传递自定义参数



**语法：**事件绑定的位置改造成<font color='red'>箭头函数的写法</font>，在执行clickHandler实际处理业务函数的时候传递实参

![image-20250820141516566](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141516566.png)

<font color='red'>注意：</font>不能直接写函数调用，这里事件绑定需要一个函数引用



## 4.4 同时传递事件对象和自定义参数



**语法：**在事件绑定的位置传递事件实参e和自定义参数，clickHandler中声明形参，注意顺序对应

![image-20250820141601395](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141601395.png)

# 5. React中的组件



## 5.1 组件是什么



**概念：**一个组件就是用户界面的一部分，它可以有自己的逻辑和外观，组件之间可以互相嵌套，也可以复用多次

![image-20250820141658841](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820141658841.png)

组件化开发可以让开发者像搭积木一样构建一个完整的庞大的应用



## 5.2 React组件



在React中，一个组件就是<font color='red'>首字母大写的函数</font>，内部存放了组件的逻辑和视图UI, 渲染组件只需要把组件<font color='red'>当成标签书写</font>即可

![image-20250820143226926](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143226926.png)

![image-20250820143242874](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143242874.png)

# 6. useState



## useState基础使用



useState 是一个 React Hook（函数），它允许我们向组件添加一个<font color='red'>状态变量</font>, 从而控制影响组件的渲染结果

![image-20250820143338656](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143338656.png)

**本质：**和普通JS变量不同的是，状态变量一旦发生变化组件的视图UI也会跟着变化<font color='red'>（数据驱动视图）</font>

![image-20250820143404078](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143404078.png)



# 7. 修改状态的规则



## 7.1 状态不可变



在React中，状态被认为是只读的，我们应该始终<font color='red'>替换它而不是修改它</font>，直接修改状态不能引发视图更新

![image-20250820143505079](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143505079.png)

![image-20250820143512184](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143512184.png)



## 7.2 修改对象状态



规则：对于对象类型的状态变量，应该始终传给set方法一个<font color='red'>全新的对象</font>来进行修改

![image-20250820143604225](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143604225.png)

![image-20250820143611783](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143611783.png)

# 8. 组件的样式处理



## 8.1 组件基础样式方案



React组件基础的样式控制有俩种方式
1. 行内样式（不推荐）

![image-20250820143653275](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820143653275.png)

2. class类名控制

![image-20250820144105022](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144105022.png)

# 案例：B站评论



## 1. B站评论案例



![image-20250820144139932](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144139932.png)

1. 渲染评论列表
2. 删除评论实现
3. 渲染导航Tab和高亮实现
4. 评论列表排序功能实现



## 2. 渲染评论列表



![image-20250820144210533](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144210533.png)

**核心思路：**

1. 使用useState维护评论列表
2. 使用map方法对列表数据进行遍历渲染（别忘了加key）



## 3. 实现评论删除



![image-20250820144237203](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144237203.png)



**需求：**

1. 只有自己的评论才显示删除按钮
2. 点击删除按钮，删除当前评论，列表中不再显示

**核心思路：**

1. 删除显示 - 条件渲染
2. 删除功能 - 拿到当前项id以id为条件对评论列表做filter过滤



## 4. 渲染Tab+点击高亮实现



![image-20250820144340191](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144340191.png)

**需求：**

点击哪个tab项，哪个做高亮处理

**核心思路：**

点击谁就把谁的<font color='red'>type（独一无二的标识）记录</font>下来，然后和遍历时的<font color='red'>每一项的type做匹配</font>，谁匹配到就设置负责高亮的类名



## 5. classnames优化类名控制



classnames是一个简单的JS库，可以非常方便的<font color='red'>通过条件动态控制class类名的显示</font>

![image-20250820144807380](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144807380.png)

**现在的问题：**字符串的拼接方式不够直观，也容易出错

![image-20250820144825392](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144825392.png)

# 9. 受控表单绑定



## 受控表单绑定



**概念：**使用React组件的状态（useState）控制表单的状态

![image-20250820144944783](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820144944783.png)

1. 准备一个React状态值

![image-20250820145004568](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145004568.png)

2. 通过value属性绑定状态，通过onChange属性绑定状态同步的函数

![image-20250820145024575](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145024575.png)

# 10. React中获取DOM



## React中获取DOM



在 React 组件中获取/操作 DOM，需要使用 <font color='red'>useRef</font> React Hook钩子函数，分为两步：
1. 使用useRef创建 ref 对象，并与 JSX 绑定

![image-20250820145116750](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145116750.png)

2. 在DOM可用时，通过 inputRef.current 拿到 DOM 对象

![image-20250820145144829](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145144829.png)

# 案例：B站评论 — 发表评论



## 1. B站评论案例 —— 核心功能实现



![image-20250820145216534](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145216534.png)

1. 获取评论内容
2. 点击发布按钮发布评论



## 2. B站评论案例 — id处理和时间处理



![image-20250820145242794](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145242794.png)

1. rpid要求一个唯一的随机数id - <font color='red'>uuid</font>
2. ctime要求以当前时间为标准，生成固定格式 - <font color='red'>dayjs</font>



## 3. B站评论案例 — 清空内容并重新聚焦



![image-20250820145326495](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145326495.png)

1. 清空内容 - 把控制input框的value状态设置为空串
2. 重新聚焦 - 拿到input的dom元素，调用focus方法

# 11. 组件通信



## 11.1 理解组件通信



**概念：**组件通信就是<font color='red'>组件之间的数据传递</font>，根据组件嵌套关系的不同，有不同的通信方法

![image-20250820145720651](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145720651.png)



## 11.2 父传子-基础实现



![image-20250820145743310](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145743310.png)



**实现步骤**

1. 父组件传递数据 - 在子组件标签上<font color='red'>绑定属性</font>
2. 子组件接收数据 - 子组件通过<font color='red'>props参数</font>接收数据



## 11.3 父传子-props说明



1. props可传递任意的数据

数字、字符串、布尔值、数组、对象、函数、JSX

![image-20250820145848492](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145848492.png)

2. props是只读对象

子组件<font color='red'>只能读取props中的数据</font>，不能直接进行修改, 父组件的数据只能由父组件修改



## 11.4 父传子 - 特殊的prop children



**场景：**当我们把内容嵌套在子组件标签中时，父组件会自动在名为children的prop属性中接收该内容

![image-20250820145936067](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145936067.png)

![image-20250820145943736](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820145943736.png)



## 11.5 父子组件通信-子传父



![image-20250820150005285](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150005285.png)

**核心思路：**在子组件中调用父组件中的函数并传递参数

![image-20250820150016464](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150016464.png)



## 11.6 使用状态提升实现兄弟组件通信



![image-20250820150035433](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150035433.png)

**实现思路：**借助“状态提升”机制，通过父组件进行兄弟组件之间的数据传递

1. A组件先通过子传父的方式把数据传给父组件App
2. App拿到数据后通过父传子的方式再传递给B组件



## 11.7 使用Context机制跨层级组件通信



![image-20250820150102191](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150102191.png)

**实现步骤：** 

1. 使用createContext方法创建一个上下文对象Ctx（可替换名称）
2. 在顶层组件（App）中通过 Ctx.Provider 组件提供数据
3. 在底层组件（B）中通过 useContext 钩子函数获取消费数据

# 12. useEffect 的使用



## 12.1 useEffect 的概念理解



useEffect是一个React Hook函数，用于在React组件中创建不是由事件引起而是<font color='red'>由渲染本身引起的操作（副作用）</font>, 比如发送AJAX请求，更改DOM等等

![image-20250820150218013](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150218013.png)

说明：上面的组件中没有发生任何的用户事件，<font color='red'>组件渲染完毕之后</font>就需要和服务器要数据，整个过程属于<font color='red'>“只由渲染引起的操作”</font>



## 12.2 useEffect 的基础使用



需求：在组件渲染完毕之后，立刻从服务端获取频道列表数据并显示到页面中

语法：

![image-20250820150301591](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820150301591.png)

参数1是一个函数，可以把它叫做副作用函数，在函数内部可以放置要执行的操作
参数2是一个数组（可选参），在数组里放置依赖项，不同依赖项会影响第一个参数函数的执行，<font color='red'>当是一个空数组的时候，副作用函数只会在组件渲染完毕之后执行一次</font>

> 接口地址：http://geek.itheima.net/v1_0/channels



## 12.3 useEffect 依赖项参数说明



useEffect副作用函数的执行时机存在多种情况，根据<font color='red'>传入依赖项的不同</font>，会有不同的执行表现

|     依赖项     |         副作用函数执行时机          |
| :------------: | :---------------------------------: |
|   没有依赖项   |    组件初始渲染 + 组件更新时执行    |
|   空数组依赖   |       只在 初始渲染时执行一次       |
| 添加特定依赖项 | 组件初始渲染 + 特性依赖项变化时执行 |

- 没有依赖项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250927230036487.png" alt="image-20250927230036487" style="zoom: 67%;" />

- 空数组依赖项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250927230105915.png" alt="image-20250927230105915" style="zoom:80%;" />

- 有特定依赖项

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250927230249161.png" alt="image-20250927230249161" style="zoom:80%;" />



## 12.4 useEffect — 清除副作用



在useEffect中编写的<font color='red'>由渲染本身引起的对接组件外部的操作</font>，社区也经常把它叫做<font color='red'>副作用操作</font>，比如在useEffect中开启了一个定时器，我们想在组件卸载时把这个定时器再清理掉，这个过程就是清理副作用

![image-20250820151052867](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820151052867.png)

**说明：**清除副作用的函数<font color='red'>最常见</font>的执行时机是在<font color='red'>组件卸载时自动执行</font>

**需求：**在Son组件渲染时开启一个定制器，卸载时清除这个定时器

# 13. 自定义Hook实现



## 自定义Hook函数



**概念：**自定义Hook是以<font color='red'> use 打头的函数</font>，通过自定义Hook函数可以用来实现<font color='red'>逻辑的封装和复用</font>

![image-20250820151154735](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820151154735.png)

# 14. React Hooks使用规则



## ReactHooks使用规则



使用规则
1. 只能在组件中或者其他自定义Hook函数中调用
2. 只能在组件的顶层调用，不能嵌套在 if、for、其他函数中

![image-20250820151232368](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820151232368.png)

# 案例：优化B站评论案例



## 1. 优化需求



![image-20250820151306487](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820151306487.png)

1. 使用请求接口的方式获取评论列表并渲染
2. 使用自定义Hook函数封装数据请求的逻辑
3. 把评论中的每一项抽象成一个独立的组件实现渲染



## 2. 优化需求-通过接口获取评论列表



1. 使用 <font color='red'>json-server</font> 工具模拟接口服务, 通过 <font color='red'>axios</font> 发送接口请求

  json-server是一个快速以.json文件作为数据源模拟接口服务的工具

  axios是一个广泛使用的前端请求库

2. 使用<font color='red'> useEffect</font> 调用接口获取数据 

![image-20250820152802810](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820152802810.png)



## 3.优化需求-封装评论项Item组件



![image-20250820152838447](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820152838447.png)

抽象原则：App作为“智能组件”负责数据的获取，Item作为“UI组件”负责数据的渲染

# 15. Redux



## 15.1 Redux快速上手



### 15.1.2 什么是Redux？



Redux 是React最常用的<font color='red'>集中状态管理工具</font>，类似于Vue中的Pinia（Vuex），<font color='red'>可以独立于框架运行</font>

**作用：**通过集中管理的方式管理应用的状态

![image-20250820153027330](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820153027330.png)



### 15.1.3 Redux快速体验



不和任何框架绑定，不使用任何构建工具，使用纯Redux实现计数器

![image-20250820153156149](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820153156149.png)

**使用步骤：**

1. 定义一个 <font color='red'>reducer 函数</font> （根据当前想要做的修改返回一个新的状态）
2. 使用createStore方法传入 reducer函数 生成一个<font color='red'>store实例对象</font>
3. 使用store实例的 <font color='red'>subscribe方法</font> 订阅数据的变化（数据一旦变化，可以得到通知）
4. 使用store实例的 <font color='red'>dispatch方法提交action对象</font> 触发数据变化（告诉reducer你想怎么改数据）
5. 使用store实例的 <font color='red'>getState方法</font> 获取最新的状态数据更新到视图中



### 15.1.4 Redux管理数据流程梳理



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250820153256436.png" alt="image-20250820153256436"  />

为了职责清晰，数据流向明确，Redux把整个数据修改的流程分成了<font color='red'>三个核心概念</font>，分别是：<font color='red'>state、action和reducer</font>
1. state - 一个对象 存放着我们管理的数据状态
2. action - 一个对象 用来描述你想怎么改数据
3. reducer - 一个函数 更具action的描述生成一个新的state



## 15.2 Redux与React - 环境准备



### 15.2.1 配套工具



在React中使用redux，官方要求安装俩个其他插件 - <font color='red'>Redux Toolkit 和 react-redux</font>

1. Redux Toolkit（RTK）- 官方推荐编写Redux逻辑的方式，是一套工具的集合集，<font color='red'>简化书写方式</font>

![image-20250826140654786](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826140654786.png)

2. react-redux - 用来 <font color='red'>链接 Redux 和 React组件</font> 的中间件

![image-20250826140720191](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826140720191.png)



### 15.2.2 配置基础环境



1. 使用 CRA 快速创建 React 项目

  ```bash
  npx create-react-app react-redux
  ```

2. 安装配套工具

  ```bash
  npm i @reduxjs/toolkit react-redux
  ```

3. 启动项目

  ```bash
  npm run start
  ```



### 15.2.3 store目录结构设计



![image-20250826155213093](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826155213093.png)

1. 通常集中状态管理的部分都会单独创建一个单独的 `store` 目录
2. 应用通常会有很多个子store模块，所以创建一个 `modules` 目录，在内部编写业务分类的子store
3. store中的入口文件 index.js 的作用是组合modules中所有的子模块，并导出store



## 15.3 Redux与React - 实现counter



### 15.3.1 整体路径熟悉



![image-20250826155301623](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826155301623.png)



### 15.3.2 使用React Toolkit 创建 counterStore



![image-20250826155324761](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826155324761.png)



### 15.3.3 为React注入store



react-redux负责把Redux和React 链接 起来，内置 Provider组件 通过 store 参数把创建好的store实例注入到应用中，链接正式建立

![image-20250826155349165](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826155349165.png)



### 15.3.4 React组件使用store中的数据



在React组件中使用store中的数据，需要用到一个 钩子函数 - useSelector，它的作用是把store中的数据映射到组件中，使用样例如下：

![image-20250826155441152](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826155441152.png)

React组件中修改store中的数据需要借助另外一个hook函数 -<font color='red'> useDispatch</font>，它的作用是生成提交action对象的dispatch函数，使用样例如下:

![image-20250826160137812](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160137812.png)



### 15.3.5 总结



1. 组件中使用哪个hook函数获取store中的数据？

  <font color='red'>useSelector</font>

2. 组件中使用哪个hook函数获取dispatch方法？

  <font color='red'>useDispatch</font>

3. 如何得到要提交action对象？

  <font color='red'>执行store模块中导出的actionCreater方法</font>



## 15.4 Redux与React - 提交action传参



### 15.4.1 需求说明



![image-20250826160309473](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160309473.png)

组件中有俩个按钮 `add to 10` 和 `add to 20` 可以直接把count值修改到对应的数字，目标count值是在组件中传递过去的，需要在<font color='red'>提交action的时候传递参数</font>



### 15.4.2 提交action传参实现需求



在reducers的同步修改方法中<font color='red'>添加action对象参数</font>，在<font color='red'>调用actionCreater的时候传递参数</font>，参数会被传递到<font color='red'>action对象payload属性</font>上

![image-20250826160420315](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160420315.png)



## 15.5 Redux与React - 异步状态操作



### 15.5.1 需求理解



![image-20250826160530972](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160530972.png)



### 15.5.2 异步操作样板代码



![image-20250826160559310](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160559310.png)

![image-20250826160609995](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160609995.png)

![image-20250826160619639](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826160619639.png)

1. 创建store的写法保持不变，配置好同步修改状态的方法

2. 单独封装一个函数，在函数内部return一个新函数，在新函数中

  2.1 封装异步请求获取数据
  2.2 调用<font color='red'>同步actionCreater</font>传入异步数据生成一个action对象，并使用dispatch提交

3. 组件中dispatch的写法保持不变



## 15.6 Redux调试 - devtools



### 15.6.1 安装chrome调试工具



Redux官方提供了针对于Redux的调试工具，支持实时state信息展示，action提交信息查看等

![image-20250826161647939](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250826161647939.png)

# 案例：美团外卖



## 1. 案例演示和环境准备



### 1.1 案例演示



![image-20250827154858973](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827154858973.png)

![image-20250827154907112](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827154907112.png)

基本开发思路：使用 RTK（Redux Toolkit）来管理应用状态, 组件负责 数据渲染 和 dispatch action



### 1.2 准备并熟悉环境



1. 克隆项目到本地（<font color='red'>内置了基础静态组件和模版</font>）

  ```bash
  git clone http://git.itcast.cn/heimaqianduan/redux-meituan.git
  ```

2. 安装所有依赖

  ```bash
  npm i
  ```

3. 启动mock服务（<font color='red'>内置了json-server</font>）

  ```bash
  npm run serve
  ```

4. 启动前端服务

  ```bash
  npm run start
  ```



## 2. 分类和商品列表渲染



### 2.1 需求理解



![image-20250827155223038](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155223038.png)



### 2.2 实现步骤



![image-20250827155253985](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155253985.png)



## 3. 点击分类激活交互实现



### 3.1 理解需求



![image-20250827155328027](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155328027.png)



### 3.2 步骤分析



![image-20250827155350032](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155350032.png)



## 4. 商品列表切换显示



### 4.1 需求理解



![image-20250827155420571](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155420571.png)



## 5. 添加购物车实现



### 5.1 需求理解



![image-20250827155500322](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155500322.png)



### 5.2 实现步骤



![image-20250827155522861](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155522861.png)



## 6. 统计区域功能实现



### 6.1 需求理解



![image-20250827155602931](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155602931.png)



### 6.2 实现步骤



![image-20250827155619926](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155619926.png)



## 7. 购物车列表功能实现



### 7.1 需求理解



![image-20250827155710676](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155710676.png)



### 7.2 实现步骤



![image-20250827155729832](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155729832.png)



## 8. 控制购物车显示和隐藏



### 8.1 需求理解



![image-20250827155818721](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155818721.png)



### 8.2 实现步骤



![image-20250827155838631](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827155838631.png)

# 16. ReactRouter



## 16.1 快速开始



### 16.1.1 什么是前端路由



一个路径 path 对应一个组件 component 当我们在浏览器中访问一个 path 的时候，path 对应的组件会在页面中进行渲染

![image-20250827160049490](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827160049490.png)



### 16.1.2 创建路由开发环境



使用路由我们还是采用CRA创建项目的方式进行基础环境配置
1. 创建项目并安装所有依赖

  ```bash
  npx create-react-app react-router-pro
  npm i
  ```
2. 安装最新的 ReactRouter包

  ```bash
  npm i react-router-dom
  ```
3. 启动项目

  ```bash
  npm run start
  ```



### 16.1.3 快速开始



**需求：**创建一个可以切换登录页和文章页的路由系统

![image-20250827161134328](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161134328.png)

![image-20250827161142064](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161142064.png)



## 16.2 抽象路由模块



###  实际开发中的router配置



![image-20250827161255261](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161255261.png)



## 16.3 路由导航



### 16.3.1 什么是路由导航



路由系统中的多个路由之间需要进行<font color='red'>路由跳转</font>，并且在跳转的同时有可能需要<font color='red'>传递参数进行通信</font>

![image-20250827161357364](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161357364.png)



### 16.3.2 声明式导航



声明式导航是指通过在模版中通过<font color='red'> `<Link/> ` 组件描述出要跳转到哪里</font>去，比如后台管理系统的左侧菜单通常使用这种方式进行

![image-20250827161444003](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161444003.png)

**语法说明：**通过给组件的<font color='red'>to属性指定要跳转到路由path</font>，组件会被渲染为浏览器支持的a链接，如果需要传参直接<font color='red'>通过字符串拼接</font>的方式拼接参数即可



### 16.3.3 编程式导航



编程式导航是指通过<font color='red'> `useNavigate` </font>钩子得到导航方法，然后通过<font color='red'>调用方法以命令式的形式</font>font>进行路由跳转，比如想在登录请求完毕之后跳转就可以选择这种方式，更加灵活

![image-20250827161632946](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161632946.png)

**语法说明：**通过调用navigate方法传入地址path实现跳转



## 16.4 导航传参



###  路由导航传参



![image-20250827161738779](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161738779.png)



## 16.5 嵌套路由配置



### 16.5.1 什么是嵌套路由



在一级路由中又内嵌了其他路由，这种关系就叫做嵌套路由，嵌套至一级路由内的路由又称作二级路由，例如：

![image-20250827161822744](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161822744.png)



### 16.5.2 嵌套路由配置



实现步骤：
1. 使用<font color='red'> children </font>属性配置路由嵌套关系
2. 使用<font color='red'> `<Outlet/>` </font>组件配置二级路由渲染位置

![image-20250827161924303](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827161924303.png)



## 16.6 默认二级路由



### 场景和配置方式



当访问的是一级路由时，默认的二级路由组件可以得到渲染，只需要在二级路由的位置<font color='red'>去掉path，设置index属性为true</font>

![image-20250827162005610](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162005610.png)



## 16.7 404路由配置



### 16.7.1 404路由



场景：当浏览器输入url的路径在整个路由配置中都找不到对应的 path，为了用户体验，可以使用 404 兜底组件进行渲染

**实现步骤：**

1. 准备一个NotFound组件
2. 在路由表数组的末尾，以*号作为路由path配置路由

![image-20250827162101215](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162101215.png)



## 16.8 两种路由模式



各个主流框架的路由常用的路由模式有俩种，<font color='red'>history模式和hash模式</font>, ReactRouter分别由 createBrowerRouter 和createHashRouter 函数负责创建

| 路由模式 |   url表现   |          底层原理           | 是否需要后端支持 |
| :------: | :---------: | :-------------------------: | :--------------: |
| history  |  url/login  | history对象 + pushState事件 |       需要       |
|   hash   | url/#/login |     监听 hashChange事件     |      不需要      |

# 案例：React极客园项目



## 1.使用CRA初始化项目环境



1. 使用CRA创建项目

  ```bash
  npx create-react-app react-jike
  ```
2. 按照业务规范整理项目目录（<font color='red'>重点SRC目录</font>）

![image-20250827162509573](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162509573.png)

![image-20250827162517766](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162517766.png)



## 2. 配置SCSS预处理器，支持嵌套语法



**SCSS是什么**

SCSS是一种<font color='red'>预编译CSS语言</font>，支持一些原生CSS不支持的高级用法，比如变量使用，<font color='red'>嵌套语法</font>等，使用SCSS可以让样式代码<font color='red'>更加高效灵活</font>

![image-20250827162614773](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162614773.png)



## 3. 安装Ant Design 组件库



**Ant Design 是什么**

Ant Design 是由蚂蚁金服出品的社区使用最广的React <font color='red'>PC端组件库</font>，内置了常用的<font color='red'>现成组件</font>，可以帮助我们快速开发PC管理后台项目

**安装AntD到项目**

1. npm i antd
2. 引入Button组件进行渲染测试

![image-20250827162705538](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162705538.png)



## 4. 配置基础路由Router



**配置步骤**

1. 安装路由包 <font color='red'>react-router-dom</font>
2. 准备俩个基础路由组件<font color='red'> Layout 和 Login</font>
3. 在router/index.js文件中引入组件进行路由配置，导出<font color='red'>router实例</font>
4. 在入口文件中渲染<font color='red'>` <RouterProvider/>`</font>，传入router实例



## 5. 配置@别名路径



**什么是@别名路径？**

通过@替代src路径，方便开发过程中的路径查找访问

![image-20250827162905942](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827162905942.png)

**如何配置？**

1. 针对路径转换，修改webpack别名路径配置 <font color='red'>craco</font>
2. 针对联想提示，修改VSCode配置 <font color='red'>jsconfig.json</font>



## 6. 使用gitee管理项目



**目的：**为了记录每次阶段性的功能，采取git管理我们的项目，方便复习

**实现步骤**

1. 在gitee上初始化一个空项目仓库
2. 把远程仓库和本地仓库关联
3. 提交代码到远程仓库



## 7. 登录



### 7.1 准备基础静态结构



使用 AntD现成的组件 创建登录页的内容结构

![image-20250827163032080](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163032080.png)

**主要组件：**Card、Form、Input、Button



### 7.2 表单校验实现



表单校验可以在提交登录之前<font color='red'>校验用户的输入是否符合预期</font>，如果不符合就阻止提交, 显示错误信息

![image-20250827163133130](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163133130.png)



### 7.3 获取表单数据



当用户输入了正确的表单内容，点击确认按钮时需要<font color='red'>收集到用户当前输入的内容</font>，用来提交接口请求

![image-20250827163204299](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163204299.png)

**解决方案：**给Form组件绑定<font color='red'>onFinish回调函数</font>，通过回调函数的参数获取用户输入的内容



### 7.4 封装request请求模块



在整个项目中会发送很多网络请求，使用axios三方库做好统一封装，方便<font color='red'>统一管理和复用</font>
1. 几乎所有的接口都是一样的接口域名
2. 几乎所有的接口都需要设置一样的超时时间
3. 几乎所有的接口都需要做Token权限处理
4. ....

![image-20250827163259471](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163259471.png)



### 7.5 使用Redux管理token



Token作为一个用户的标识数据，需要在<font color='red'>很多个模块中共享</font>，Redux可以方便的解决状态共享问题

![image-20250827163656852](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163656852.png)

1. Redux中编写获取Token的异步获取和同步修改
2. Login组件负责提交action并且把表单数据传递过来



### 7.6 Token持久化



**现存问题**

Redux存入Token之后如果<font color='red'>刷新浏览器</font>，Token会丢失（持久化就是防止刷新时丢失Token）

**问题原因**

Redux是基于浏览器内存的存储方式，刷新时状态恢复为初始值

![image-20250827163738805](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163738805.png)

**技术方案**

![image-20250827163751611](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163751611.png)



### 7.7 封装Token的存取删方法



**封装的原因？**

对于Token的各类操作在项目<font color='red'>多个模块中都有用到</font>，为了<font color='red'>共享复用</font>可以封装成工具函数

![image-20250827163852558](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827163852558.png)



## 8. Axios请求拦截器注入Token



**为什么要做这件事儿？**

Token作为用户的一个标识数据，<font color='red'>后端很多接口</font>都会以它作为接口权限判断的依据；请求拦截器注入Token之后，所有用到Axios实例的接口请求都<font color='red'>自动携带了Token</font>

![image-20250827164138129](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164138129.png)



## 9. 使用Token做路由权限控制



**具体要做什么事儿？**

有些路由页面内的内容信息比较敏感，如果用户没有经过登录获取到有效Token，是没有权限跳转的，<font color='red'>根据Token的有无控制当前路由是否可以跳转</font>就是路由的权限控制

**技术方案**

![image-20250827164251816](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164251816.png)



## 10. Layout



### 10.1 结构创建和样式初始化



**静态结构搭建**

![image-20250827164637007](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164637007.png)

**样式初始化**

安装 Normalize.css



### 10.2 二级路由配置



![image-20250827164707246](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164707246.png)



### 10.3 菜单点击跳转路由实现



**实现效果：**点击左侧菜单可以跳转到对应的目标路由

**思路分析**

1. 左侧菜单要和路由形成<font color='red'>一一对应的关系</font>（知道点了谁）
2. 点击时拿到路由<font color='red'>路径</font>调用<font color='red'>路由方法跳转</font>（跳转到对应的路由下面）

![image-20250827164750769](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164750769.png)



### 10.4 根据当前路由路径高亮菜单



**实现效果：**页面在刷新时可以根据当前的路由路径让对应的左侧菜单高亮显示

![image-20250827164828133](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164828133.png)

思路分析
1. 获取当前url上的路由路径
2. 找到菜单组件负责高亮的属性，绑定当前的路由路径



### 10.5 展示个人信息



![image-20250827164854300](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164854300.png)

**关键问题：**用户信息应该放到哪里维护？

和Token令牌类似，用户的信息通常很有可能在多个组件中都需要<font color='red'>共享使用</font>，所以同样应该放到<font color='red'>Redux中维护</font>

![image-20250827164918009](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827164918009.png)



### 10.6 退出登录实现



退出登录是一个通用的业务逻辑，退出登录都要做什么？

![image-20250827165254098](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165254098.png)

1. 提示用户是否确认要退出（<font color='red'>危险操作，二次确认</font>）
2. 用户确认之后清除用户信息（<font color='red'>Token以及其它个人信息</font>）
3. 跳转到登录页（<font color='red'>为下次登录做准备</font>）



### 10.7 处理Token失效



**什么是Token失效？**

为了用户的安全和隐私考虑，在用户<font color='red'>长时间未在网站中做任何操作</font>且<font color='red'>规定的失效时间到达之后</font>，当前的Token就会失效，一旦失效，不能再作为用户令牌标识请求隐私数据

**前端如何知道Token已经失效了？**

通常在Token失效之后再去请求接口，后端会返回<font color='red'>401状态码</font>，前端可以监控这个状态做后续的操作

**Token失效了前端做什么？**

![image-20250827165431372](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165431372.png)



## 11. Home-Echarts



### 11.1 基础图表实现



![image-20250827165452784](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165452784.png)

三方图表插件如何在项目中快速使用起来？
1. 按照三方插件文档中的<font color='red'>“快速开始”</font>，快速跑起来Demo
2. 按照业务需求修改配置项做定制处理

注意：1. 图表的初始化在<font color='red'>useEffect</font>中完成 2. 挂载渲染的节点需要有宽高



### 11.2 组件封装实现



为什么要做组件封装？

组件封装主要解决了<font color='red'>复用</font>的问题

![image-20250827165636101](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165636101.png)

以上俩个图表除了Title不一样之外，其余部分都一样，把不一样的部分<font color='red'>抽象成props参数</font>做适配

![image-20250827165654260](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165654260.png)



## 12. 拓展-API模块封装



**现存问题**

当前的接口请求放到了功能实现的位置，没有在固定的模块内维护，后期查找维护困难

**解决思路**

把项目中的所有接口按照业务模块<font color='red'>以函数的形式</font>统一封装到apis模块中

![image-20250827165731746](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250827165731746.png)



## 13. 文章发布



**功能演示说明**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175425315.png" alt="image-20251006175425315" style="zoom:50%;" />



## 14. 基础文章发布



### 14.1 创建并熟悉基础结构



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175502237.png" alt="image-20251006175502237" style="zoom:50%;" />

1. 面包屑导航组件 Breadcrumb
2. 表单组件 Form
3. 输入框组件 Input
4. 下拉框组件 Select - Option
5. 按钮组件 Button



### 14.2 准备富文本编辑器



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175543517.png" alt="image-20251006175543517" style="zoom:50%;" />

1. 安装<font color='red'> react-quill</font> 富文本编辑器

  ```
  npm i react-quill@2.0.0-beta.2
  ```
2. 导入编辑器组件和配套样式文件
3. 渲染编辑器组件
4. 调整编辑器组件样式



### 14.3 频道数据获取渲染



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175627054.png" alt="image-20251006175627054" style="zoom:50%;" />

1. 根据接口文档在APIS模块中封装接口函数
2. 使用 <font color='red'>useState</font> 维护数据
3. 在 <font color='red'>useEffect</font> 中调用接口获取数据并存入state
4. 绑定数据到下拉框组件



### 14.4 收集表单数据提交表单



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175716713.png" alt="image-20251006175716713" style="zoom:50%;" />



## 15. 上传文章封面基础功能实现



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175755145.png" alt="image-20251006175755145" style="zoom:50%;" />



## 16. 实现切换封面类型



**实现效果：**只有当前模式为单图或者三图模式时才显示上传组件

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006175858823.png" alt="image-20251006175858823" style="zoom:50%;" />



## 17. 控制上传图片的数量



**实现的效果**

1. 单图模式时，最多能上传一张图片
2. 三图模式时，最多能上传三张图片

**如何实现**

1. 找到限制上传数量的组件属性
2. 使用imageType进行绑定控制



## 18. 发布带封面的文章



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180033700.png" alt="image-20251006180033700" style="zoom:50%;" />



## 19. 文章列表模块



### 19.1 功能描述和静态结构创建



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180104007.png" alt="image-20251006180104007" style="zoom:50%;" />



### 19.2 渲染频道数据



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180124105.png" alt="image-20251006180124105" style="zoom:50%;" />

可选的方案：
1. 直接再写一遍
2. 存到Redux中维护
3. <font color='red'>使用自定义业务hook</font>



### 19.3 渲染table文章列表



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180231737.png" alt="image-20251006180231737" style="zoom: 50%;" />

1. 封装请求接口
2. 使用useState维护状态数据
3. 使用useEffect发送请求



### 19.4 适配文章状态



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180258331.png" alt="image-20251006180258331" style="zoom:50%;" />

**实现效果**：根据文章的不同状态在状态列显示不同Tag

**实现思路**

1. 如果要适配的状态只有俩个 - 三元条件渲染
2. 如果要适配的状态有多个 - 枚举渲染



### 19.5 筛选功能实现

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180346859.png" alt="image-20251006180346859" style="zoom:50%;" />

筛选功能的本质：给<font color='red'>请求列表接口传递不同的参数</font>和后端要不同的数据

**实现步骤：**

1. <font color='red'>准备完整的请求参数对象</font>
2. 获取用户选择的表单数据
3. 把表单数据放置到接口对应的字段中
4. 重新调用文章列表接口渲染Table列表



### 19.6 分页功能实现



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180429057.png" alt="image-20251006180429057" style="zoom:50%;" />

实现效果：点击页数，在Table中显示当前页的数据列表

**如何实现：**

1. 实现分页展示 （<font color='red'>页数 = 总数 / 每页条数</font>）
2. 点击分页拿到当前点击的页数
3. 使用页数作为请求参数重新获取文章列表渲染



### 19.7 删除功能实现



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180500669.png" alt="image-20251006180500669" style="zoom: 50%;" />

**实现效果：**点击删除按钮删除当前文章

**如何实现：**

1. 点击删除弹出确认框
2. 得到文章id，使用id调用删除接口
3. 更新文章列表



### 19.8 编辑文章跳转



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180533861.png" alt="image-20251006180533861" style="zoom:50%;" />

**实现效果：**点击编辑文章跳转到文章编辑页

**如何实现：**

1. 获取当前文章id
2. 跳转到创建（编辑）文章的路由



## 20. 编辑文章



### 20.1 回填基础数据



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180618397.png" alt="image-20251006180618397" style="zoom:50%;" />

**实现效果：**把页面中除了封面之外的其余字段完成回填

**如何实现：**

1. 通过文章id获取到文章详情数据
2. 调用Form组件实例方法 <font color='red'>setFieldsValue</font> 回显数据



### 20.2 回填封面信息



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180702436.png" alt="image-20251006180702436" style="zoom:50%;" />

**实现效果：**回填封面的类型以及上传过的封面图片

**如何实现：**

1. 使用cover中的type字段回填封面类型
2. 使用cover中的images字段回填封面图片



### 20.3 根据id适配状态



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180733088.png" alt="image-20251006180733088" style="zoom:50%;" />

**实现效果：**发布文章时显示发布文章，编辑文章状态下显示编辑文章

**如何实现：**

<font color='red'>核心就是看是否有id</font>，有文章id代表编辑状态，没有文章id代表发布状态



### 20.4 更新文章



**实现效果：**当用户对文章内容做修改之后，点击确认更新文章内容

**如何实现：**

更新文章和新增文章相比，大部分的逻辑都是一致的，<font color='red'>稍作参数适配调用不同接口</font>即可

1. 适配url参数

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006180925464.png" alt="image-20251006180925464" style="zoom:50%;" />

2. 调用文章更新接口



## 21. 项目打包和本地预览



1. **项目打包**

  打包指的是将项目中的<font color='red'>源代码和资源文件进行处理</font>，生成可在生产环境中运行的<font color='red'>静态文件</font>的过程
  **打包命令**：npm run build

  

2. **本地预览（模拟服务器运行项目）**

  本地预览是指在本地通过静态服务器模拟生产服务器运行项目的过程

  1. 安装本地服务包 

  	```
  	npm i -g serve
  	```

  2. ```

  	serve -s ./build
  	```

  3. 浏览器中访问 http://localhost:3000/



## 22. 打包优化



### 22.1 配置路由懒加载



**什么是路由懒加载？**

路由懒加载是指路由的JS资源只有在被访问时才会动态获取，目的是为了<font color='red'>优化项目首次打开的时间</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006213832272.png" alt="image-20251006213832272" style="zoom:50%;" />

**如何进行配置？**

1. 把路由修改为由React提供的 <font color='red'>lazy 函数进行动态导入</font>
2. 使用React内置的<font color='red'> Suspense组件</font> 包裹路由中element选项对应的组件



### 22.2 包体积分析



**什么包体积分析？**

通过可视化的方式，直观的体现项目中各种包打包之后的体积大小，方便做优化

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006213922099.png" alt="image-20251006213922099" style="zoom:50%;" />

怎么做到？<font color='red'>source-map-explorer</font>
1. 安装包 2. 配置命令指定要分析的js文件



### 22.3 CDN优化



**什么是CDN?**

CDN是一种内容分发网络服务，当用户请求网站内容时，由<font color='red'>离用户最近的服务器</font>将<font color='red'>缓存的</font>资源内容传递给用户

**哪些资源可以放到CDN服务器？**

体积较大的<font color='red'>非业务JS文件</font>, 比如react、react-dom

1. 体积较大，需要利用CDN文件在浏览器的缓存特性，加快加载时间
2. 非业务JS文件，不需要经常做变动，CDN不用频繁更新缓存

**项目中怎么做？**

1. 把需要做CDN缓存的文件排除在打包之外（react、react-dom）
2. 以CDN的方式重新引入资源（react、react-dom）



# 17. 性能优化相关API

> useMemo/React.memo/useCallback



## 17.1 useReducer



**作用**：和useState的作用类似，用来管理<font color='red'>相对复杂</font>的状态数据

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214148456.png" alt="image-20251006214148456" style="zoom:50%;" />



### 17.1.1 基础用法



1. 定义一个reducer函数（根据不同的action返回不同的新状态）
2. 在组件中调用useReducer，并传入reducer函数和状态的初始值
3. 事件发生时，通过dispatch函数分派一个action对象（通知reducer要返回哪个新状态并渲染UI）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214221978.png" alt="image-20251006214221978" style="zoom:50%;" />



### 17.1.2 分派action时传参



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214242574.png" alt="image-20251006214242574" style="zoom:50%;" />



### 17.1.3 小结



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214304015.png" alt="image-20251006214304015" style="zoom:50%;" />



## 17.2 useMemo



**作用：**在组件每次重新渲染的时候<font color='red'>缓存计算的结果</font>

看个需求：

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214346581.png" alt="image-20251006214346581" style="zoom:50%;" />

**基础语法**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214442171.png" alt="image-20251006214442171" style="zoom:50%;" />

**说明：**使用useMemo做缓存之后可以保证只有count1依赖项发生变化时才会重新计算



## 17.3 React.memo



**作用：**允许组件在<font color='red'>Props没有改变</font>的情况下跳过渲染

React组件默认的渲染机制：只要父组件重新渲染子组件就会重新渲染

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214612087.png" alt="image-20251006214612087" style="zoom:50%;" />

思考：如果Son组件本身并不需要做渲染更新，是不是存在浪费？



### 17.3.1 基础语法



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214638518.png" alt="image-20251006214638518" style="zoom:50%;" />

**说明：**经过memo函数包裹生成的缓存组件只有在props发生变化的时候才会重新渲染



### 17.3.2 props的比较机制



**机制:** 在使用memo缓存组件之后，React会对<font color='red'>每一个 prop</font> 使用 <font color='red'>Object.is</font> 比较新值和老值，返回true，表示没有变化

prop是简单类型

<font color='red'>Object.is(3, 3) => true</font> 没有变化

prop是引用类型（对象 / 数组）

<font color='red'>Object([], []) => false</font> 有变化，React只关心引用是否变化



## 17.4 useCallback



**作用：**在组件多次重新渲染的时候缓存函数



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214802503.png" alt="image-20251006214802503" style="zoom:50%;" />



### 17.4.1 基础语法



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214829933.png" alt="image-20251006214829933" style="zoom:50%;" />

**说明：**使用useCallback包裹函数之后，函数可以保证在App<font color='red'>重新渲染的时候保持引用稳定</font>

# 18. React.forwardRef

> 使用ref暴露DOM节点给父组件



**forwardRef - 场景说明**



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006214945182.png" alt="image-20251006214945182" style="zoom:50%;" />

**forwardRef - 语法实现**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006215000192.png" alt="image-20251006215000192" style="zoom:50%;" />

# 19. useInperativeHandle

> 通过ref暴露子组件中的方法



**useInperativeHandlle - 场景说明**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006215050554.png" alt="image-20251006215050554" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006215107047.png" alt="image-20251006215107047" style="zoom:50%;" />

# 20. Class API

> 编写类组件



## 20.1 类组件基础结构



类组件就是通过<font color='red'>JS中的类来组织组件的代码</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006215745571.png" alt="image-20251006215745571" style="zoom:50%;" />

1. 通过类<font color='red'>属性state</font>定义状态数据 
1. 通过<font color='red'>setState方法</font>来修改状态数据
1. 通过<font color='red'>render</font>来写UI模版（JSX语法一致）



## 20.2 类组件的生命周期函数



**概念：**组件从创建到销毁的各个阶段自动执行的函数就是生命周期函数

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006215845251.png" alt="image-20251006215845251" style="zoom:50%;" />

1. componentDidMount：组件挂载完毕自动执行 - <font color='red'>异步数据获取</font>
2. componentWillUnmount: 组件卸载时自动执行 - <font color='red'>清理副作用</font>



## 20.3 类组件的组件通信



**概念：**类组件和Hooks编写的组件在组件通信的<font color='red'>思想上完全一致</font>

1. 父传子：通过prop绑定数据
2. 子传父：通过prop绑定父组件中的函数，子组件调用
3. 兄弟通信：状态提升，通过父组件做桥接

# 21. zustand

> 极简的状态管理工具



## 21.1 快速上手



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220030124.png" alt="image-20251006220030124" style="zoom:50%;" />



## 21.2 异步支持



对于异步的支持不需要特殊的操作，直接在函数中编写异步逻辑，最后只需要<font color='red'>调用set方法传入新状态</font>即可

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220102437.png" alt="image-20251006220102437" style="zoom:50%;" />



## 21.3 切片模式



**场景：**当单个store比较大的时候，可以采用 <font color='red'>切片模式</font> 进行模块拆分组合，类似于模块化

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220137368.png" alt="image-20251006220137368" style="zoom:50%;" />

# 22. React与TypeScript

> 开发环境创建



**基于Vite创建开发环境**



Vite是一个<font color='red'>框架无关的前端工具链</font>，可以快速的生成一个 React + TS 的开发环境，并且可以提供快速的开发体验

```
npm create vite@latest react-ts-pro -- --template react-ts
```

**说明：**

1. npm create vite@latest 固定写法 （使用最新版本vite初始化项目）
2. react-ts-pro 项目名称 （可以自定义）
3. -- --template react-ts 指定项目模版位react+ts

# 23. useState与TypeScript



## 23.1 useState-自动推导



通常React会根据传入<font color='red'>useState的默认值</font>来自动推导类型,不需要显式标注类型

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220349138.png" alt="image-20251006220349138" style="zoom:50%;" />

**说明：**

1. value: 类型为boolean
2. toggle: 参数类型为boolean



## 23.2 useState-传递泛型参数



useState本身是一个<font color='red'>泛型函数</font>，可以传入具体的自定义类型

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220421712.png" alt="image-20251006220421712" style="zoom:50%;" />

**说明：**

1. 限制useState函数参数的初始值必须满足类型为： User | （）=> User
2. 限制setUser函数的参数必须满足类型为：User | （）=> User | undefined
3. user状态数据具备User类型相关的类型提示



## 23.3 useState-初始值为null



当我们不知道状态的初始值是什么，将useState的<font color='red'>初始值为null</font>是一个常见的做法，可以通过<font color='red'>具体类型联合null</font>来做显式注解

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220500425.png" alt="image-20251006220500425" style="zoom:50%;" />

**说明：**

1. 限制useState函数参数的初始值可以是 User | null
2. 限制setUser函数的参数类型可以是 User | null

# 24. 事件与TypeScript



**为事件回调添加类型**



为事件回调添加类型约束需要使用<font color='red'>React内置的泛型函数</font>来做，比如最常见的鼠标点击事件和表单输入事件：

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220549836.png" alt="image-20251006220549836" style="zoom:50%;" />

**说明：**通过泛型函数约束了<font color='red'>整个事件回调函数的类型</font>，主要是为了约束事件参数e的类型

# 25. Props与TypeScript



## 25.1 基础使用



为组件prop添加类型，本质是给<font color='red'>函数的参数做类型注解</font>，可以使用<font color='red'>type对象类型或者interface接口</font>来做注解

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220644296.png" alt="image-20251006220644296" style="zoom:50%;" />

**说明：**Button组件只能传入名称为className的prop参数，类型为string, 且为必填



## 25.2 为children添加类型



children是一个比较特殊的prop, 支持多种不同类型数据的传入，需要通过一个<font color='red'>内置的ReactNode类型</font>来做注解

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220726273.png" alt="image-20251006220726273" style="zoom:50%;" />

**说明：**注解之后，children可以是多种类型，包括：React.ReactElement 、string、number、React.ReactFragment 、React.ReactPortal 、boolean、 null 、undefined



## 25.3 为事件prop添加类型



组件经常执行类型为函数的prop实现子传父，这类prop重点在于函数参数类型的注解

![image-20251006220816125](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220816125.png)

**说明：**

1. 在组件内部调用时需要遵守类型的约束，参数传递需要满足要求
2. 绑定prop时如果绑定内联函数直接可以推断出参数类型，否则需要单独注解匹配的参数类型

# 26. useRef与TypeScript



## 26.1 获取dom



获取dom的场景，可以直接把要获取的<font color='red'>dom元素的类型当成泛型参数传递给useRef</font>,可以推导出<font color='red'>.current属性的类型</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006220951379.png" alt="image-20251006220951379" style="zoom:50%;" />



## 26.2 引用稳定的存储器



把useRef当成引用稳定的存储器使用的场景可以通过<font color='red'>泛型传入联合类型</font>来做，比如定时器的场景：

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221018255.png" alt="image-20251006221018255" style="zoom:50%;" />

# 极客园移动端

> 项目开发环境创建



## 1. 基于Vite创建开发环境



Vite是一个<font color='red'>框架无关的前端工具链</font>，可以快速的生成一个 React + TS 的开发环境，并且可以提供快速的开发体验

```
npm create vite@latest react-jike-mobile -- --template react-ts
```

**说明：**

1. npm create vite@latest 固定写法 （使用最新版本vite初始化项目）
2. react-ts-pro 项目名称 （可以自定义）
3. -- --template react-ts 指定项目模版位react+ts



## 2. 安装Ant Design Mobile



Ant Design Mobile 是 Ant Design 家族里专门针对于移动端的组件库

看文档！



## 3. 初始化路由



React的路由初始化，我们采用 <font color='red'>react-router-dom</font> 进行配置

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221237551.png" alt="image-20251006221237551" style="zoom:50%;" />



## 4. 配置路径别名



**场景：**项目中各个模块之间的互相导入导出，可以通过@别名路径做路径简化，经过配置@相当于src目录，比如：

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221324269.png" alt="image-20251006221324269" style="zoom:50%;" />

**步骤：**

1. 让Vite做路径解析（真实的路径转换）
2. 让VSCode做智能路径提示（开发者体验）



## 5. 安装axios



**场景：**axios作为最流行的请求插件，同样是类型友好的，基于axios做一些基础的封装

1. 安装axios到项目
2. 在utils中封装http模块，主要包括<font color='red'>接口基地址、超时时间、拦截器</font>
3. 在utils中做统一导出



## 6. 封装API模块



### 6.1 axios和ts的配合使用



**场景：**axios提供了request泛型方法，方便我们<font color='red'>传入类型参数推导出接口返回值的类型</font>

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221440829.png" alt="image-20251006221440829" style="zoom:50%;" />

**说明：**泛型参数 <font color='red'>Type 的类型决定了 res.data 的类型</font>

**步骤：**

1. 根据接口文档创建一个通用的泛型接口类型（多个接口返回值的结构是相似的）
2. 根据接口文档创建特有的接口数据类型（每个接口有自己特殊的数据格式）
3. 组合1和2的类型，得到最终传给request泛型的参数类型

**流程图:**

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221528929.png" alt="image-20251006221528929" style="zoom:50%;" />



## 7. Home模块



### 7.1 整体组件嵌套设计



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221611550.png" alt="image-20251006221611550" style="zoom:50%;" />



### 7.2 Tabs区域实现



<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221634174.png" alt="image-20251006221634174" style="zoom:50%;" />

**实现步骤：**

1. 使用 ant-mobile 组件库中的 Tabs 组件进行页面结构创建
2. 使用真实接口数据进行渲染
3. 有优化的点进行优化处理



### 7.3 自定义hook函数优化（可选）



**场景：**当前状态数据的各种操作逻辑和组件渲染是写在一起的，可以采用<font color='red'>自定义hook封装的方式让逻辑和渲染相分离</font>

**实现步骤：**

1. 把和Tabs相关的响应式数据状态以及操作数据的方法放到hook函数中
2. 组件中调用hook函数，消费其返回的状态和方法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221716645.png" alt="image-20251006221716645" style="zoom:50%;" />



### 7.4 List组件实现



**实现步骤：**

1. 搭建基础结构，并获取基础数据
2. 为组件设计 channelId 参数，点击tab时传入不同的参数
3. 实现上拉加载功能

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006221754818.png" alt="image-20251006221754818" style="zoom:50%;" />



### 7.5 List列表无限滚动实现



**交互要求：**List列表在滑动到底部时，自动加载下一页列表数据

**实现思路：**

1. 滑动到底部触发加载下一页动作

  ```
  <InfiniteScroll/>
  ```

2. 加载下一页数据

  ```
  pre_timestamp 接口参数
  ```

3. 把老数据和新数据做拼接处理

  ```
  [...oldList, ... newList]
  ```

4. 停止监听边界值

  ```
  hasMore
  ```



### 7.6 详情模块-路由跳转&数据渲染



**需求：**点击列表中的某一项跳转到详情路由并显示当前文章

1. 通过路由跳转方法进行跳转，并传递参数
2. <font color='red'>在详情路由下获取参数，并请求数据</font>
3. 渲染数据到页面中

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20251006222854573.png" alt="image-20251006222854573" style="zoom:50%;" />
