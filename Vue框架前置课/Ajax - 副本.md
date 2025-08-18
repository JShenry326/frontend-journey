# 一、Ajax入门





## 1. Ajax概念和axios使用





### 1.1 什么是 AJAX



**定义：**

![image-20250413171854096](../images/image-20250413171854096.png)



**概念：**

AJAX 是浏览器与服务器进行数据通信的技术

<img src="../images/image-20250413173407095.png" alt="image-20250413173407095" style="zoom:50%;" />



### 1.2 怎么用 AJAX ？



1. 先使用 axios 库，与服务器进行<font color='red'>数据通信</font>
  - 基于 XMLHttpRequest 封装、代码简单、月下载量在 14 亿次
  - <font color='red'>Vue、React 项目中都会用到 axios</font> 
2. 再学习 XMLHttpRequest 对象的使用，了解 AJAX 底层原理



### 1.3 axios 使用



**语法：**

1. 引入 axios.js：https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js
2. 使用 axios 函数
  - 传入<font color='red'>配置对象</font>
  - 再用<font color='red'> .then</font> 回调函数接收结果，并做后续处理

<img src="../images/image-20250513165729626.png" alt="image-20250513165729626" style="zoom:50%;" />

**示例：**

需求：请求目标资源地址，拿到省份列表数据，显示到页面

目标资源地址：http://hmajax.itheima.net/api/province

<img src="../images/image-20250513165805796.png" alt="image-20250513165805796" style="zoom:50%;" />



## 2. 认识 URL



原因：知道作用和组成，方便与后端人员沟通

<img src="../images/image-20250513165903510.png" alt="image-20250513165903510" style="zoom:50%;" />

<img src="../images/image-20250513165911643.png" alt="image-20250513165911643" style="zoom:50%;" />



### 2.1 什么是 URL？



**定义：**

<img src="../images/image-20250513165958911.png" alt="image-20250513165958911" style="zoom:50%;" />

**例如：**

- https://www.baidu.com/index.html	              →网页资源

- https://www.itheima.com/images/logo.png          →图片资源

- http://hmajax.itheima.net/api/province                →数据资源

	

	概念：URL 就是<font color='red'>统一资源定位符</font>，简称<font color='red'>网址</font>，用于访问网络上的<font color='red'>资源</font>

	

### 2.2 URL 的组成



**组成：**

<img src="../images/image-20250513170216632.png" alt="image-20250513170216632" style="zoom:50%;" />

**<font color='red'>协议</font>**

**http 协议：**超文本传输协议，规定浏览器和服务器之间传输数据的<font color='red'>格式</font>

<img src="../images/image-20250513170302740.png" alt="image-20250513170302740" style="zoom:50%;" />



**<font color='#5e9ede'>域名</font>**

**域名：**标记服务器在互联网中<font color='red'>方位</font>

<img src="../images/image-20250513170435545.png" alt="image-20250513170435545" style="zoom:50%;" />

<font color='#01b154'>**资源路径**</font>

**资源路径：**标记资源在服务器下的<font color='red'>具体位置</font>

<img src="../images/image-20250513170534811.png" alt="image-20250513170534811" style="zoom:50%;" />



### 2.3 示例



获取 - 新闻列表

**需求：**使用 axios 从服务器拿到新闻列表数据
目标资源地址：http://hmajax.itheima.net/api/news

<img src="../images/image-20250513170628166.png" alt="image-20250513170628166" style="zoom:50%;" />



## 3. URL 查询参数



**定义**：浏览器提供给服务器的<font color='red'>额外信息</font>，让服务器返回浏览器想要的数据

**语法**：http://xxxx.com/xxx/xxx?参数名1=值1&参数名2=值2

<img src="../images/image-20250513170901948.png" alt="image-20250513170901948" style="zoom:50%;" />



### 3.1 axios－查询参数



**语法**：使用 axios 提供的 <font color='red'>params </font>选项

**注意**：axios 在运行时把参数名和值，会拼接到 url<font color='red'>?参数名=值</font>

**城市列表**：http://hmajax.itheima.net/api/city?pname=河北省

<img src="../images/image-20250513171103102.png" alt="image-20250513171103102" style="zoom:50%;" />



## 4. 常用请求方法和数据提交



### 4.1 请求方法



对服务器<font color='red'>资源</font>，要执行的<font color='red'>操作</font>

<img src="../images/image-20250513171209413.png" alt="image-20250513171209413" style="zoom:50%;" />



### 4.2 数据提交



**场景：**当数据需要在服务器上<font color='red'>保存</font>

<img src="../images/image-20250513171332378.png" alt="image-20250513171332378" style="zoom:50%;" />

<img src="../images/image-20250513171339143.png" alt="image-20250513171339143" style="zoom:50%;" />



### 4.3 axios 请求配置



**url：**请求的 URL 网址

**<font color='red'>method</font>：**请求的方法，<font color='red'>GET</font>可以省略（不区分大小写）

**<font color='red'>data</font>**：提交数据

<img src="../images/image-20250513171443866.png" alt="image-20250513171443866" style="zoom:50%;" />



### 4.4 数据提交－注册账号



**需求：**通过 axios 提交用户名和密码，完成注册功能

注册用户 URL 地址：http://hmajax.itheima.net/api/register

**请求方法**：<font color='red'>POST</font>

**参数名：**

<font color='red'>username</font> 用户名（中英文和数字组成，最少 8 位）
<font color='red'>password</font> 密码（最少 6 位）

<img src="../images/image-20250513171549854.png" alt="image-20250513171549854" style="zoom:50%;" />

<img src="../images/image-20250513171557782.png" alt="image-20250513171557782" style="zoom:50%;" />



### 4.6 axios 的核心配置



➢ url：请求 URL 网址
➢ <font color='red'>method</font>：请求方法，<font color='red'>GET</font> 可以省略（不区分大小写）
➢ params：查询参数
➢ <font color='red'>data</font>：提交数据

从服务器中查询数据：

<img src="../images/image-20250513204834631.png" alt="image-20250513204834631" style="zoom:50%;" />

提交数据到服务器中：

<img src="../images/image-20250513204820827.png" alt="image-20250513204820827" style="zoom:50%;" />



### 4.7 axios 错误处理



**场景：**再次注册相同的账号，会遇到报错信息

**处理：**用更直观的方式，给<font color='red'>普通用户</font>展示错误信息

<img src="../images/image-20250513171726037.png" alt="image-20250513171726037" style="zoom:50%;" />

<img src="../images/image-20250513171733822.png" alt="image-20250513171733822" style="zoom:50%;" />



**语法：**在 <font color='red'>then</font> 方法的后面，通过点语法调用 <font color='red'>catch</font> 方法，传入<font color='red'>回调函数</font>并定义<font color='red'>形参</font>

<img src="../images/image-20250513171857331.png" alt="image-20250513171857331" style="zoom:50%;" />

**处理**：注册案例，重复注册时通过弹框提示用户错误原因



## 5. HTTP协议-报文



**HTTP 协议：**规定了浏览器发送及服务器返回内容的<font color='red'>格式</font>



### 5.1 请求报文



**<font color='red'>请求报文</font>：**浏览器按照 HTTP 协议要求的<font color='red'>格式</font>，发送给服务器的<font color='red'>内容</font>

<img src="../images/image-20250513171958750.png" alt="image-20250513171958750" style="zoom:50%;" />



#### 1.请求报文的格式



请求报文的组成部分有:
1. <font color='red'>请求行：请求方法，URL，</font>协议
2. <font color='red'>请求头：</font>以键值对的格式携带的附加信息，比如：<font color='red'>Content-Type</font>
3. 空行：分隔请求头，空行之后的是发送给服务器的资源
4. <font color='red'>请求体：发送的资源</font>

<img src="../images/image-20250513172052056.png" alt="image-20250513172052056" style="zoom:50%;" />

<img src="../images/image-20250513172147932.png" alt="image-20250513172147932" style="zoom:50%;" />

<img src="../images/image-20250513172059793.png" alt="image-20250513172059793" style="zoom:50%;" />



通过 Chrome 的<font color='red'>网络面板</font>查看请求报文

<img src="../images/image-20250513172207692.png" alt="image-20250513172207692" style="zoom:50%;" />



#### 2. 请求报文－错误排查



需求：通过请求报文排查错误原因，并修复

输入<font color='red'>正确</font>的用户名和密码无法登录

• 用户名：<font color='red'>itheima007</font>
• 密码：<font color='red'>7654321</font>

<img src="../images/image-20250513172346030.png" alt="image-20250513172346030" style="zoom:50%;" />



### 5.2 响应报文


<font color='red'>**响应报文**</font>：服务器按照 HTTP 协议要求的<font color='red'>格式</font>，返回给浏览器的<font color='red'>内容</font>

1. <font color='red'>响应行（状态行）</font>：协议、<font color='red'>HTTP 响应状态码</font>、状态信息
2. <font color='red'>响应头</font>：以键值对的格式携带的附加信息，比如：<font color='red'>Content-Type</font>
3. 空行：分隔响应头，空行之后的是服务器返回的资源
4. <font color='red'>响应体：返回的资源</font>

<img src="../images/image-20250513172828265.png" alt="image-20250513172828265" style="zoom:50%;" />

<img src="../images/image-20250513172837413.png" alt="image-20250513172837413" style="zoom: 50%;" />



#### 1. HTTP 响应状态码



HTTP 响应状态码：用来表明请求<font color='red'>是否成功</font>完成

比如：<font color='red'>404（服务器找不到资源）</font>

<img src="../images/image-20250513172934668.png" alt="image-20250513172934668" style="zoom:50%;" />

<img src="../images/image-20250513172942761.png" alt="image-20250513172942761" style="zoom:50%;" />



## 6. 接口文档



<font color='red'>接口文档：</font>描述<font color='red'>接口</font>的文章<font color='red'>（后端工程师）</font>

<font color='red'>接口：</font>使用 AJAX 和服务器通讯时，使用的 <font color='red'>URL，请求方法，以及参数</font>

<font color='red'>传送门：</font>AJAX 阶段接口文档https://apifox.com/apidoc/shared/1b0dd84f-faa8-435d-b355-5a8a329e34a8)

<img src="../images/image-20250513173116574.png" alt="image-20250513173116574" style="zoom:50%;" />



## 7. 案例 - 用户登录



1. 点击登录时，判断用户名和密码长度
2. 提交数据和服务器通信
3. 提示信息

<img src="../images/image-20250513173149155.png" alt="image-20250513173149155" style="zoom:50%;" />

<img src="../images/image-20250513173158584.png" alt="image-20250513173158584" style="zoom:50%;" />

<img src="../images/image-20250513173215482.png" alt="image-20250513173215482" style="zoom:50%;" />



## 8. form-serialize 插件



**作用：**<font color='red'>快速</font>收集表单元素的值

插件js文件存储在C:\Users\Lenovo\Desktop\课程实践\Vue框架前置课\Ajax\day01\lib中

<img src="../images/image-20250513173248901.png" alt="image-20250513173248901" style="zoom:50%;" />

<img src="../images/image-20250513173259064.png" alt="image-20250513173259064" style="zoom:50%;" />

**语法：**

<img src="../images/image-20250513173316146.png" alt="image-20250513173316146" style="zoom:50%;" />

<img src="../images/image-20250513224930171.png" alt="image-20250513224930171" style="zoom:50%;" />

**hash值为true时：**结果为JS对象<font color='red'>（更推荐）</font>

<img src="../images/image-20250513225032337.png" alt="image-20250513225032337" style="zoom:50%;" />

**hash值为false时：**结果为查询字符串

<img src="../images/image-20250513225132192.png" alt="image-20250513225132192" style="zoom:50%;" />

**empty值为true时：**获取空值<font color='red'>（更推荐）</font>

<img src="../images/image-20250513225252333.png" alt="image-20250513225252333" style="zoom:50%;" />

**empty值为false时：**不获取空值

<img src="../images/image-20250513225324915.png" alt="image-20250513225324915" style="zoom:50%;" />



### 8.1 案例－用户登录



使用 form-serialize 插件，<font color='red'>收集</font>用户名和密码

<img src="../images/image-20250513173342244.png" alt="image-20250513173342244" style="zoom:50%;" />



# 二、Ajax综合案例



## 1. 案例-图书管理



步骤：
1. Bootstrap 弹框
2. 渲染列表（查）
3. 新增图书（增）
4. 删除图书（删）
5. 编辑图书（改）

<img src="../images/image-20250514170601429.png" alt="image-20250514170601429" style="zoom:50%;" />



### 1.1 Bootstrap 弹框



功能：不离开当前页面，显示单独内容，供用户操作

bootstarp官网：[Bootstrap中文网](https://www.bootcss.com/)

步骤：

1. 引入 bootstrap.css 和 bootstrap.js

```html
<!-- 引入bootstrap.css -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet">
<!-- 引入bootstrap.js -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.min.js"></script>
```

2. 准备<font color='red'>弹框标签</font>，确认结构

3. 通过<font color='red'>自定义属性</font>(data-bs-toggle,data-bs-target,data-bs-dismiss)，控制弹框的<font color='red'>显示</font>和<font color='red'>隐藏</font>



<img src="../images/image-20250514170702129.png" alt="image-20250514170702129" style="zoom:50%;" />

1. 通过属性控制，弹框显示或隐藏		*单纯显示/隐藏*	如上左图
2. 通过 JS 控制，弹框显示或隐藏	         *额外逻辑代码*	 如下右图



<img src="../images/image-20250514170755889.png" alt="image-20250514170755889" style="zoom:50%;" />



### 1.2 图书管理 - 渲染列表



自己的图书数据：给自己起个<font color='red'>外号</font>，并告诉服务器，默认会有三本书，基于这三本书做数据的<font color='red'>增删改查</font>

<img src="../images/image-20250514195900520.png" alt="image-20250514195900520" style="zoom:50%;" />

核心步骤 - 渲染数据

<img src="../images/image-20250514200131694.png" alt="image-20250514200131694" style="zoom:50%;" />



### 1.3 图书管理 - 新增图书



<img src="../images/image-20250514195956216.png" alt="image-20250514195956216" style="zoom:50%;" />

核心步骤 - 新增数据

<img src="../images/image-20250514200149754.png" alt="image-20250514200149754" style="zoom:50%;" />





### 1.4 图书管理 - 删除图书



<img src="../images/image-20250514200018086.png" alt="image-20250514200018086" style="zoom:50%;" />

核心步骤 - 删除数据

<img src="../images/image-20250514200205170.png" alt="image-20250514200205170" style="zoom:50%;" />





### 1.5 图书管理 - 编辑图书



<img src="../images/image-20250514200039069.png" alt="image-20250514200039069" style="zoom:50%;" />

核心步骤 - 编辑数据

<img src="../images/image-20250514200226726.png" alt="image-20250514200226726" style="zoom:50%;" />

<img src="../images/image-20250514200240253.png" alt="image-20250514200240253" style="zoom: 50%;" />



## 2. 图片上传



1. 获取图片文件对象
2. 使用 FormData 携带图片文件

<img src="../images/image-20250514200315296.png" alt="image-20250514200315296" style="zoom:50%;" />

3. 提交表单数据到服务器，使用图片 url 网址

<img src="../images/image-20250514200325244.png" alt="image-20250514200325244" style="zoom:50%;" />



## 3. 案例 - 网站换肤



1. 选择图片上传，设置body背景
2. 上传成功时，保存url网址
3. 网页运行后，获取url网址使用

<img src="../images/image-20250514200440471.png" alt="image-20250514200440471" style="zoom:50%;" />



## 4. 案例 - 个人信息设置



步骤：
1. 信息渲染
2. 头像修改
3. 提交表单
4. 结果提示

<img src="../images/image-20250514200451799.png" alt="image-20250514200451799" style="zoom:50%;" />



### 4.1 个人信息设置 - 信息渲染



自己的用户信息：给自己起个<font color='red'>外号</font>，并告诉服务器，获取对应的用户信息

<img src="../images/image-20250514200518858.png" alt="image-20250514200518858" style="zoom:50%;" />



### 4.2 个人信息设置 - 头像修改



<img src="../images/image-20250514200535916.png" alt="image-20250514200535916" style="zoom:50%;" />



### 4.3 个人信息设置 - 信息修改



<img src="../images/image-20250514200552836.png" alt="image-20250514200552836" style="zoom:50%;" />



### 4.4 个人信息设置 - 提示框



<img src="../images/image-20250514200610230.png" alt="image-20250514200610230" style="zoom:50%;" />



# 三、Ajax原理



## 1. XMLHttpRequest



**定义：**

![image-20250516174156106](../images/image-20250516174156106.png)

**关系：**axios 内部采用 XMLHttpRequest 与服务器交互

<img src="../images/image-20250516174210429.png" alt="image-20250516174210429" style="zoom:50%;" />

**好处：**掌握使用 XHR 与服务器进行数据交互，了解 axios 内部原理

> AJAX 原理是什么？
> XMLHttpRequest 对象



### 1.1 使用 XMLHttpRequest



**步骤：**

1. 创建 XMLHttpRequest 对象
2. 配置<font color='red'>请求方法</font>和请求 <font color='red'>url </font>地址
3. 监听 loadend 事件，接收<font color='red'>响应结果</font>
4. 发起请求

<img src="../images/image-20250516174305261.png" alt="image-20250516174305261" style="zoom:50%;" />



**示例：**获取并展示所有省份名字

<img src="../images/image-20250516174333170.png" alt="image-20250516174333170" style="zoom:50%;" />



### 1.2 XMLHttpRequest - 查询参数



**定义：**浏览器提供给服务器的<font color='red'>额外信息</font>，让服务器返回浏览器想要的数据

**语法：**http://xxxx.com/xxx/xxx<font color='red'>?</font>font>参数名1=值1<font color='red'>&</font>参数名2=值2

<img src="../images/image-20250516174512355.png" alt="image-20250516174512355" style="zoom:50%;" />



**示例：**地区查询



需求：输入省份和城市名字，查询地区列表

请求地址：http://hmajax.itheima.net/api/area?参数名1=值1&参数名2=值2

<img src="../images/image-20250516174548549.png" alt="image-20250516174548549" style="zoom:50%;" />

<img src="../images/image-20250516174554196.png" alt="image-20250516174554196" style="zoom:50%;" />



### 1.3 XMLHttpRequest - 数据提交



**需求：**通过 XHR 提交用户名和密码，完成注册功能

**核心：**

<font color='red'>请求头</font>设置 Content-Type：application/json

<font color='red'>请求体</font>携带 JSON 字符串

<img src="../images/image-20250516175033071.png" alt="image-20250516175033071" style="zoom:50%;" />

<img src="../images/image-20250516175040891.png" alt="image-20250516175040891" style="zoom:50%;" />

​	

## 2. Promise



**定义：**

<img src="../images/image-20250516223604558.png" alt="image-20250516223604558" style="zoom:50%;" />

**好处：**

1. 逻辑更清晰，成功和失败状态，可以关联对应处理程序
2. 了解 axios 函数内部运作机制
3. 能解决回调函数地狱问题



**语法：**

<img src="../images/image-20250516223625031.png" alt="image-20250516223625031" style="zoom:50%;" />

<img src="../images/image-20250516223643979.png" alt="image-20250516223643979" style="zoom:50%;" />



### 2.1 Promise - 三种状态



**作用：**了解Promise对象如何<font color='red'>关联</font>的<font color='red'>处理函数</font>，以及代码执行顺序

**概念：**一个Promise对象，必然处于以下几种状态之一

✓ 待定（pending） ：初始状态，既没有被兑现，也没有被拒绝
✓ 已兑现（fulfilled） ：意味着，操作成功完成
✓ 已拒绝（rejected） ：意味着，操作失败

<img src="../images/image-20250516223808235.png" alt="image-20250516223808235" style="zoom:50%;" />

> [!CAUTION]
>
> 注意：Promise对象一旦被<font color='red'>兑现/拒绝</font>就是<font color='red'>已敲定</font>了，状态无法再被改变



**示例：**使用Promise + XHR 获取省份列表

**需求：**使用 Promise 管理 XHR 获取省份列表，并展示到页面上

**步骤：**

1. 创建 Promise 对象
2. 执行 XHR 异步代码，获取省份列表
3. 关联成功或失败函数，做后续处理

<img src="../images/image-20250516223921992.png" alt="image-20250516223921992" style="zoom:50%;" />



## 3. 封装简易版 axios



### 3.1 获取省份列表



需求：基于 Promise + XHR 封装 myAxios 函数，获取省份列表展示

步骤：

1. 定义 myAxios 函数，接收<font color='red'>配置对象</font>，返回 <font color='red'>Promise 对象</font>
2. 发起 <font color='red'>XHR 请求，默认请求方法</font>为 GET
3. 调用成功/失败的处理
4. 使用 myAxios 函数，获取省份列表展示

<img src="../images/image-20250517174836238.png" alt="image-20250517174836238" style="zoom:50%;" />

<img src="../images/image-20250517174843011.png" alt="image-20250517174843011" style="zoom:50%;" />

<img src="../images/image-20250517175139544.png" alt="image-20250517175139544" style="zoom:50%;" />



### 3.2 获取地区列表



需求：修改 myAxios 函数支持传递<font color='red'>查询参数</font>，获取"辽宁省"，"大连市"对应地区列表展示

步骤：

1. myAxios 函数调用后，判断 <font color='red'>params </font>选项
2. 基于 URLSearchParams 转换<font color='red'>查询参数字符串</font>
3. 使用自己封装的 myAxios 函数展示地区列表

<img src="../images/image-20250517174934159.png" alt="image-20250517174934159" style="zoom:50%;" />

<img src="../images/image-20250517175206988.png" alt="image-20250517175206988" style="zoom:50%;" />

<img src="../images/image-20250517175216973.png" alt="image-20250517175216973" style="zoom:50%;" />



### 3.3 注册用户



需求：修改 myAxios 函数支持传递<font color='red'>请求体</font>数据，完成注册用户功能

步骤：

1. myAxios 函数调用后，判断 <font color='red'>data </font>选项
2. 转换数据类型，在<font color='red'> send 方法</font>中发送
3. 使用自己封装的 myAxios 函数完成注册用户功能

<img src="../images/image-20250517175035170.png" alt="image-20250517175035170" style="zoom:50%;" />

<img src="../images/image-20250517175244435.png" alt="image-20250517175244435" style="zoom:50%;" />

<img src="../images/image-20250517175322128.png" alt="image-20250517175322128" style="zoom:50%;" />



## 4. 案例 - 天气预报



步骤：
1. 获取北京市天气数据，展示
2. 搜索城市列表，展示
3. 点击城市，显示对应天气数据

<img src="../images/image-20250517175416441.png" alt="image-20250517175416441" style="zoom:50%;" />



### 4.1 搜索城市列表



需求：根据关键字，展示匹配城市列表

步骤：

1. 绑定 input 事件，获取关键字
2. 获取展示城市列表数据

<img src="../images/image-20250517175444566.png" alt="image-20250517175444566" style="zoom:50%;" />



### 4.2 展示城市天气



需求：展示用户搜索查看的城市天气

步骤：

1. 检测搜索列表点击事件，获取城市 code 值
2. 复用获取展示城市天气函数

<img src="../images/image-20250517175510517.png" alt="image-20250517175510517" style="zoom:50%;" />



# 四、Ajax进阶



## 1. 同步代码和异步代码



### 1.1 同步代码和异步代码



同步代码：[异步 JavaScript 简介 - 学习 Web 开发 | MDN](https://developer.mozilla.org/zh-CN/docs/Learn_web_development/Extensions/Async_JS/Introducing#同步编程)

<img src="../images/image-20250519151932668.png" alt="image-20250519151932668" style="zoom:50%;" />

异步代码：[异步 JavaScript 简介 - 学习 Web 开发 | MDN](https://developer.mozilla.org/zh-CN/docs/Learn_web_development/Extensions/Async_JS/Introducing)

<img src="../images/image-20250519152016410.png" alt="image-20250519152016410" style="zoom:50%;" />



同步代码：逐行执行，需<font color='red'>原地等待结果</font>后，才继续向下执行

异步代码：调用后<font color='red'>耗时</font>，不阻塞代码继续执行（不必原地等待），在将来完成后触发一个<font color='red'>回调函数</font>



> [!NOTE]
>
> JS 中有哪些异步代码？
>
> ➢ setTimeout / setInterval
> ➢ 事件
> ➢ AJAX
>
> 
>
> 异步代码如何接收结果？
>
> ➢ 依靠<font color='red'>回调函数</font>来接收



### 1.2 同步和异步



例子：回答打印数字的顺序是什么？

<img src="../images/image-20250519152118400.png" alt="image-20250519152118400" style="zoom: 50%;" />

打印结果：1,4,2
点击按钮一次就打印一次 3

异步代码接收结果：使用<font color='red'>回调函数</font>



## 2. 回调函数地狱和 Promise 链式调用



### 2.1 回调函数地狱

需求：展示默认第一个省，第一个城市，第一个地区在下拉菜单中

概念：在回调函数中<font color='red'>嵌套回调函数</font>，一直嵌套下去就形成了回调函数地狱

缺点：可读性差，异常无法捕获，耦合性严重，牵一发动全身

<img src="../images/image-20250519152322675.png" alt="image-20250519152322675" style="zoom:50%;" />

<img src="../images/image-20250519152329400.png" alt="image-20250519152329400" style="zoom:50%;" />



### 2.2 Promise - 链式调用



概念：依靠 then() 方法会返回一个<font color='red'>新生成的 Promise 对象</font>特性，继续串联下一环任务，直到结束

细节：then() 回调函数中的<font color='red'>返回值</font>，会影响新生成的 Promise 对象<font color='red'>最终状态和结果</font>

好处：通过链式调用，解决回调函数嵌套问题

<img src="../images/image-20250519152443125.png" alt="image-20250519152443125" style="zoom:50%;" />



**Promise 链式应用**

目标：使用 Promise 链式调用，解决回调函数地狱问题

做法：每个 Promise 对象中管理一个异步任务，用 then 返回 Promise 对象，串联起来

![image-20250519152500896](../images/image-20250519152500896.png)

<img src="../images/image-20250519152534269.png" alt="image-20250519152534269" style="zoom:50%;" />



## 3. async 和 await 使用



### 3.1 async函数和await



定义：[async function - JavaScript | MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/async_function)

<img src="../images/image-20250519201659838.png" alt="image-20250519201659838" style="zoom:50%;" />

概念： 在 async 函数内，使用 await 关键字取代 then 函数，<font color='red'>等待</font>获取 Promise 对象<font color='red'>成功状态的结果值</font>

示例：

<img src="../images/image-20250519201850848.png" alt="image-20250519201850848" style="zoom:67%;" />



### 3.2 async函数和await_捕获错误



使用：

<img src="../images/image-20250519201922909.png" alt="image-20250519201922909" style="zoom:50%;" />

语法：

<img src="../images/image-20250519201934876.png" alt="image-20250519201934876" style="zoom:50%;" />



## 4. 事件循环-EventLoop



### 4.1 认识 - 事件循环（EventLoop）



好处：掌握 JavaScript 是如何安排和<font color='red'>运行代码</font>的

<img src="../images/image-20250519213205574.png" alt="image-20250519213205574" style="zoom:50%;" />

<img src="../images/image-20250519213217475.png" alt="image-20250519213217475" style="zoom:50%;" />

**事件循环（EventLoop）**



概念：

<img src="../images/image-20250519213245625.png" alt="image-20250519213245625" style="zoom:50%;" />

原因：JavaScript 单线程（某一刻只能执行一行代码），为了让耗时代码不阻塞其他代码运行，设计了<font color='red'>事件循环模型</font>

<img src="../images/image-20250519213259208.png" alt="image-20250519213259208" style="zoom:50%;" />



### 4.2 事件循环 - 执行过程



定义：执行代码和收集异步任务的模型，在调用栈空闲，反复调用任务队列里回调函数的执行机制，就叫事件循环

<img src="../images/image-20250519213332452.png" alt="image-20250519213332452" style="zoom:50%;" />

JavaScript 内代码如何执行？

- 执行同步代码，遇到<font color='red'>异步代码</font>交给<font color='red'>宿主</font>浏览器环境执行
- 异步有了结果后，把回调函数放入<font color='red'>任务队列排队</font>
- 当调用栈<font color='red'>空闲</font>后，反复调用任务队列里的回调函数



### 4.3 宏任务与微任务



ES6 之后引入了 Promise 对象， 让 JS 引擎也可以发起异步任务

异步任务分为：

- <font color='red'>宏任务</font>：由<font color='red'>浏览器</font>环境执行的异步代码
- <font color='red'>微任务</font>：由<font color='red'>JS 引擎</font>环境执行的异步代码

<img src="../images/image-20250519213736362.png" alt="image-20250519213736362" style="zoom:50%;" />

<img src="../images/image-20250519213744392.png" alt="image-20250519213744392" style="zoom: 56%;" />

> [!CAUTION]
>
> Promise 本身是同步的，而then和catch<font color='red'>回调函数</font>是异步的



**宏任务与微任务 - 执行顺序**



<img src="../images/image-20250519213844094.png" alt="image-20250519213844094" style="zoom:50%;" />

JavaScript 内代码如何执行？

- 执行第一个 script 脚本事件宏任务，里面<font color='red'>同步</font>代码
- 遇到 <font color='red'>宏任务/微任务</font> 交给宿主环境，有结果回调函数进入对应队列
- 当执行栈空闲时，<font color='red'>清空微任务</font>队列，再执行<font color='red'>下一个宏任务</font>，从1再来

<img src="../images/image-20250519213938588.png" alt="image-20250519213938588" style="zoom:50%;" />



## 5. Promise.all 静态方法



### 5.1 Promise.all 静态方法



**概念：**合并多个 Promise 对象，等待所有<font color='red'>同时成功</font>完成（或某一个失败），做后续逻辑

<img src="../images/image-20250519214021021.png" alt="image-20250519214021021" style="zoom:50%;" />



**语法：**

<img src="../images/image-20250519214041689.png" alt="image-20250519214041689" style="zoom: 50%;" />

**需求**：同时请求“北京”，“上海”，“广州”，“深圳”的天气并在网页尽可能<font color='red'>同时</font>显示

<img src="../images/image-20250519214102282.png" alt="image-20250519214102282" style="zoom:50%;" />

<img src="../images/image-20250519214138981.png" alt="image-20250519214138981" style="zoom:50%;" />



## 6. 案例 - 商品分类



需求：尽可能同时展示所有商品分类到页面上

步骤：

1. 获取所有的一级分类数据
2. 遍历id，创建获取二级分类请求
3. 合并所有二级分类Promise对象
4. 等待同时成功，开始渲染页面

<img src="../images/image-20250519222127087.png" alt="image-20250519222127087" style="zoom:50%;" />

<img src="../images/image-20250519222210285.png" alt="image-20250519222210285" style="zoom:50%;" />

<img src="../images/image-20250519222227449.png" alt="image-20250519222227449" style="zoom:50%;" />



## 7. 案例 - 学习反馈



<img src="../images/image-20250520171425782.png" alt="image-20250520171425782" style="zoom:50%;" />



### 7.1 学习反馈 - 省市区切换



需求：完成省市区切换效果

步骤：

1. 设置<font color='red'>省份数据</font>到下拉菜单
2. 切换省份，设置<font color='red'>城市数据</font>到下拉菜单，并清空地区下拉菜单
3. 切换城市，设置<font color='red'>地区数据</font>到下拉菜单

<img src="../images/image-20250520171541257.png" alt="image-20250520171541257" style="zoom:50%;" />

<img src="../images/image-20250520171601129.png" alt="image-20250520171601129" style="zoom:50%;" />



### 7.2 学习反馈 - 数据提交



需求：收集学习反馈数据，提交保存
步骤：
1. 监听提交按钮的<font color='red'>点击事件</font>
2. 依靠插件<font color='red'>收集</font>表单数据
3. 基于 axios 提交<font color='red'>保存</font>，显示结果

<img src="../images/image-20250520171620336.png" alt="image-20250520171620336" style="zoom: 50%;" />



