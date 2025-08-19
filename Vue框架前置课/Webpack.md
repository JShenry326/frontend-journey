# Webpack



## 1. 什么是 Webpack？



**定义：**[概念 | webpack 中文文档](https://webpack.docschina.org/concepts/)

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172102956.png" alt="image-20250526172102956" style="zoom:50%;" />

**静态模块：**指的是编写代码过程中的，html，css，js，图片等固定内容的文件

**<font color='red'>打包：</font>**把静态模块内容，压缩，整合，转译等（前端工程化）

- 把 less / sass 转成 css 代码
- 把 ES6+ 降级成 ES5
- 支持多种模块标准语法

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172156249.png" alt="image-20250526172156249" style="zoom:50%;" />

> 问题：为何不学 vite ？
>
> 因为：很多项目还是基于 Webpack 构建，并为 VueReact 脚手架使用做铺垫！



## 2. 使用 Webpack



**需求：**封装 utils 包，校验手机号长度和验证码长度，在 <font color='red'>src/index.js</font> 中使用并打包观察

**步骤：**

1. 新建并初始化项目，编写业务<font color='red'>源代码</font>
2. 下载 webpack webpack-cli 到当前项目中（版本独立），并<font color='red'>配置</font>局部自定义命令
3. 运行<font color='red'>打包</font>命令，自动产生 dist 分发文件夹（压缩和优化后，用于最终运行的代码）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172347107.png" alt="image-20250526172347107" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172354253.png" alt="image-20250526172354253" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172401565.png" alt="image-20250526172401565" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172409846.png" alt="image-20250526172409846" style="zoom:50%;" />



## 3. 修改 Webpack 打包入口和出口



**Webpack 配置：**影响 Webpack 打包过程和结果（[概念 | webpack 中文文档](https://webpack.docschina.org/concepts/#entry)）

**步骤：**

1. 项目根目录，新建 <font color='red'>webpack.config.js</font> 配置文件
2. 导出<font color='red'>配置对象</font>，配置入口，出口文件的路径
3. 重新打包观察

**注意：**只有和入口产生直接/间接的引入关系，才会被打包

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526172557842.png" alt="image-20250526172557842" style="zoom:50%;" />



## 4.案例：用户登录 - 长度判断



**需求：**点击登录按钮，判断手机号和验证码长度

**步骤：**

1. 准备用户登录页面
2. 编写核心 JS 逻辑代码
3. 打包并手动复制网页到 dist 下，引入打包后的 js，运行

<font color='red'>**核心：**</font>Webpack 打包后的代码，作用在前端网页中使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526210219306.png" alt="image-20250526210219306" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526210227253.png" alt="image-20250526210227253" style="zoom:50%;" />



## 5. 自动生成 html 文件



插件 html-webpack-plugin（[HtmlWebpackPlugin | webpack 中文文档](https://webpack.docschina.org/plugins/html-webpack-plugin/)）： 在 Webpack 打包时生成 html 文件

**步骤：**

1. 下载 <font color='red'>html-webpack-plugin</font> 本地软件包
2. <font color='red'>配置</font> webpack.config.js 让 Webpack 拥有插件功能
3. 重新<font color='red'>打包</font>观察效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526212540493.png" alt="image-20250526212540493" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526212547979.png" alt="image-20250526212547979" style="zoom:50%;" />



## 6. 打包 css 代码



加载器 css-loader（[css-loader | webpack 中文文档](https://webpack.docschina.org/loaders/css-loader/)）：解析 css 代码

加载器 style-loader（[style-loader | webpack 中文文档](https://webpack.docschina.org/loaders/style-loader/)）：把解析后的 css 代码插入到 DOM

**步骤：**

1. 准备 css 文件<font color='red'>代码</font>引入到 src/login/index.js 中（压缩转译处理等）
2. <font color='red'>下载</font> css-loader 和 style-loader 本地软件包
3. <font color='red'>配置</font> webpack.config.js 让 Webpack 拥有该加载器功能
4. 打包后观察效果

**注意：**Webpack 默认只识别 js 代码

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526212739582.png" alt="image-20250526212739582" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526212912220.png" alt="image-20250526212912220" style="zoom:50%;" />



## 7. 优化



### 7.1 提取 css 代码



插件 mini-css-extract-plugin（[MiniCssExtractPlugin | webpack 中文文档](https://webpack.docschina.org/plugins/mini-css-extract-plugin/)）：提取 css 代码

**步骤：**

1. <font color='red'>下载</font> mini-css-extract-plugin 本地软件包
2. <font color='red'>配置 </font>webpack.config.js 让 Webpack 拥有该插件功能
3. 打包后观察效果

**注意：**不能和 style-loader 一起使用

**好处：**css 文件可以被浏览器缓存，减少 js 文件体积

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213048100.png" alt="image-20250526213048100" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213054897.png" alt="image-20250526213054897" style="zoom:50%;" />



### 7.2 压缩过程



**问题：**css 代码提取后没有压缩

**解决（[MiniCssExtractPlugin | webpack 中文文档](https://webpack.docschina.org/plugins/mini-css-extract-plugin/#minimizing-for-production)）：**使用 css-minimizer-webpack-plugin（[CssMinimizerWebpackPlugin | webpack 中文文档](https://webpack.docschina.org/plugins/css-minimizer-webpack-plugin/)） 插件

**步骤：**

1. <font color='red'>下载</font> css-minimizer-webpack-plugin 本地软件包
2. <font color='red'>配置</font> webpack.config.js 让 webpack 拥有该功能
3. 打包重新观察

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213624134.png" alt="image-20250526213624134" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213631663.png" alt="image-20250526213631663" style="zoom:50%;" />



## 8. 打包 less 代码



加载器 less-loader（[less-loader | webpack 中文文档](https://webpack.docschina.org/loaders/less-loader/)）：把 less 代码编译为 css 代码

步骤：

1. 新建 less <font color='red'>代码</font>（设置背景图）并引入到 src/login/index.js 中
2. <font color='red'>下载</font> less 和 less-loader 本地软件包
3. <font color='red'>配置</font> webpack.config.js 让 Webpack 拥有功能
4. 打包后观察效果

注意：less-loader 需要配合 less 软件包使用

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213800772.png" alt="image-20250526213800772" style="zoom: 50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213813160.png" alt="image-20250526213813160" style="zoom:50%;" />



## 9. 打包图片



**资源模块（[资源模块 | webpack 中文文档](https://webpack.docschina.org/guides/asset-modules/)）：**Webpack5 内置资源模块（字体，图片等）打包，无需额外 loader

**步骤：**

1. <font color='red'>配置</font> webpack.config.js 让 Webpack 拥有打包图片功能

- ✓ 占位符 【hash】对模块内容做算法计算，得到映射的数字字母组合的字符串
- ✓ 占位符 【ext】使用当前模块原本的占位符，例如：.png / .jpg 等字符串
- ✓ 占位符 【query】保留引入文件时代码中查询参数（只有 URL 下生效）

2. 打包后观察效果和区别

注意：判断临界值默认为<font color='red'> 8KB</font>

- 大于 8KB 文件：发送一个单独的文件并导出 URL 地址 
- 小于 8KB 文件：导出一个 data URI（base64字符串）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526213958730.png" alt="image-20250526213958730" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526214005551.png" alt="image-20250526214005551" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526214013158.png" alt="image-20250526214013158" style="zoom:50%;" />



## 10. 用户登录 - 完成功能



**需求：**完成登录功能的核心流程，以及 Alert 警告框使用

**步骤：**

1. 使用 npm 下载 axios（体验 npm 作用在前端项目中）
2. 准备并修改 utils 工具包源代码<font color='red'>导出</font>实现函数
3. <font color='red'>导入</font>并编写逻辑代码，打包后运行观察效果

​                                                                                                                                                   <img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526214114191.png" alt="image-20250526214114191" style="zoom: 50%;" />

![image-20250526214108872](https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526214108872.png)



## 11. 搭建开发环境



问题：之前改代码，需重新打包才能运行查看，效率很低

开发环境（[开发环境 | webpack 中文文档](https://webpack.docschina.org/guides/development/)）：配置 webpack-dev-server 快速开发应用程序

作用：启动 Web 服务，<font color='red'>自动</font>检测代码变化，<font color='red'>热更新</font>到网页

注意：dist 目录和打包内容是在内存里（更新快）

步骤：

1. <font color='red'>下载</font> webpack-dev-server 软件包到当前项目
2. 设置模式为<font color='red'>开发模式</font>，并配置<font color='red'>自定义命令</font>
3. 使用 npm run dev 来启动开发服务器，试试热更新效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526214307114.png" alt="image-20250526214307114" style="zoom:50%;" />



## 12. 打包模式



**打包模式**（[模式(Mode) | webpack 中文文档](https://webpack.docschina.org/configuration/mode/)）：告知 Webpack 使用相应模式的内置优化

**分类：**

| 模式名称 |  模式名字   |               特点               |   场景   |
| :------: | :---------: | :------------------------------: | :------: |
| 开发模式 | development | 调试代码，实时加载，模块热替换等 | 本地开发 |
| 生产模式 | production  |   压缩代码，资源优化，更轻量等   | 打包上线 |



设置：

- 方式1：在 webpack.config.js 配置文件设置 mode 选项

	

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526221315071.png" alt="image-20250526221315071" style="zoom:50%;" />

	

- 方式2：在 package.json 命令行设置 mode 参数

	

	<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526221549140.png" alt="image-20250526221549140" style="zoom:50%;" />

	

注意：命令行设置的优先级高于配置文件中的，推荐用命令行设置







## 13. 打包模式的应用



**需求：**在开发模式下用 style-loader 内嵌更快，在生产模式下提取 css 代码

**方案1（[模式(Mode) | webpack 中文文档](https://webpack.docschina.org/configuration/mode/)）：**webpack.config.js 配置导出函数，但是局限性大（只接受 2 种模式）

**方案2：**借助 cross-env （跨平台通用）包命令，设置参数区分环境

**步骤：**

1. <font color='red'>下载</font> cross-env 软件包到当前项目
2. <font color='red'>配置</font>自定义命令，传入参数名和值（会绑定到 <font color='red'>process.env</font> 对象下）
3. 在 webpack.config.js 区分不同环境<font color='red'>使用</font>不同配置
4. 重新打包观察两种配置区别

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526223120958.png" alt="image-20250526223120958" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526223128225.png" alt="image-20250526223128225" style="zoom:50%;" />

**方案3（[生产环境 | webpack 中文文档](https://webpack.docschina.org/guides/production/#setup)）：**配置不同的 webpack.config.js （适用多种模式差异性较大情况）



## 14. 前端-注入环境变量



**需求：**<font color='red'>前端</font>项目中，开发模式下打印语句生效，生产模式下打印语句失效

**问题：**cross-env 设置的只在 Node.js 环境生效，前端代码无法访问 process.env.NODE_ENV 

**解决（[DefinePlugin | webpack 中文文档](https://webpack.docschina.org/plugins/define-plugin/#root)）：**使用 Webpack 内置的 DefinePlugin 插件

**作用：**在编译时，将前端代码中匹配的变量名，替换为值或表达式

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526223250283.png" alt="image-20250526223250283" style="zoom:50%;" />



## 15. 开发环境调错 - source map



**问题**：代码被压缩和混淆，无法正确定位源代码位置（行数和列数）

**source map**（[开发环境 | webpack 中文文档](https://webpack.docschina.org/guides/development/#using-source-maps)）：可以准确追踪 error 和 warning 在原始代码的位置

**设置**：webpack.config.js 配置 devtool 选项（[Devtool | webpack 中文文档](https://webpack.docschina.org/configuration/devtool/)）

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250526223325197.png" alt="image-20250526223325197" style="zoom:50%;" />

**inline-source-map 选项：**把源码的位置信息一起打包在 js 文件内

**注意：**source map 仅适用于开发环境，不要在生产环境使用（防止被轻易查看源码位置）



## 16. 解析别名 alias



**解析别名（[解析(Resolve) | webpack 中文文档](https://webpack.docschina.org/configuration/resolve/#resolvealias)）：**配置模块如何解析，创建 import 引入路径的别名，来确保模块引入变得更简单

**例如：**原来路径如图，比较长而且相对路径不安全

**解决：**在 webpack.config.js 中配置解析别名 @ 来代表 src 绝对路径

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171506588.png" alt="image-20250527171506588" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171514791.png" alt="image-20250527171514791" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171527835.png" alt="image-20250527171527835" style="zoom:50%;" />



## 17. 优化-CDN使用



**CDN定义（[CDN - MDN Web 文档术语表：Web 相关术语的定义 | MDN](https://developer.mozilla.org/zh-CN/docs/Glossary/CDN)）**：内容分发网络，指的是一组分布在各个地区的服务器

**作用**：把静态资源文件/第三方库放在 CDN 网络中各个服务器中，供用户就近请求获取

**好处**：减轻自己服务器请求压力，就近请求物理延迟低，配套缓存策略

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171626483.png" alt="image-20250527171626483" style="zoom:50%;" />



**需求：**开发模式使用本地第三方库，生产模式下使用 CDN 加载引入

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171744493.png" alt="image-20250527171744493" style="zoom:50%;" />

步骤：
1. 在 html 中引入第三方库的 CDN 地址（[BootCDN - Bootstrap 中文网开源项目免费 CDN 加速服务 铂特优选](https://www.bootcdn.cn/)） 并用模板语法判断
2. 配置 webpack.config.js 中 externals（[外部扩展(Externals) | webpack 中文文档](https://webpack.docschina.org/configuration/externals/#root)） 外部扩展选项（防止某些 import 的包被打包）
3. 两种模式下打包观察效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171838369.png" alt="image-20250527171838369" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171852710.png" alt="image-20250527171852710" style="zoom:50%;" />

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527171859543.png" alt="image-20250527171859543" style="zoom:50%;" />



## 18. 多页面打包



**单页面（[SPA（单页应用） - MDN Web 文档术语表：Web 相关术语的定义 | MDN](https://developer.mozilla.org/zh-CN/docs/Glossary/SPA)）：**<font color='red'>单个 html</font> 文件，切换 DOM 的方式实现不同业务逻辑展示，后续 Vue/React 会学到

**多页面：**<font color='red'>多个 html</font> 文件，切换页面实现不同业务逻辑展示

**需求：**把黑马头条-数据管理平台-内容页面一起引入打包使用

**步骤：**

1. 准备<font color='red'>源码</font>（html，css，js）放入相应位置，并改用模块化语法<font color='red'>导出</font>
2. 下载 form-serialize 包并<font color='red'>导入</font>到核心代码中使用
3. 配置 webpack.config.js <font color='red'>多入口</font>和<font color='red'>多页面</font>的设置
4. 重新打包观察效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527172100269.png" alt="image-20250527172100269" style="zoom:50%;" />



## 19. 案例-发布文章页面打包



**需求：**把发布文章页面一起打包

**步骤：**

1. 准备发布文章页面<font color='red'>源代码</font>，改写成模块化的导出和导入方式
2. 修改 webpack.config.js 的<font color='red'>配置</font>，增加一个入口和出口
3. 打包观察效果



## 20. 优化-分割公共代码



**需求：**把 2 个以上页面引用的公共代码提取

**步骤：**

1. <font color='red'>配置</font> webpack.config.js 的 splitChunks 分割功能
2. <font color='red'>打包</font>观察效果

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527172213055.png" alt="image-20250527172213055" style="zoom:50%;" />



------

<img src="https://ossjshenry.oss-cn-hangzhou.aliyuncs.com/img/image-20250527172229696.png" alt="image-20250527172229696" style="zoom:50%;" />

