# 1. React介绍



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

1. 使用createContext方法创建一个上下文对象Ctx
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
|   空数组依赖   |       只在初始渲染时执行一次        |
| 添加特定依赖项 | 组件初始渲染 + 特性依赖项变化时执行 |



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

# 15.Redux



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
