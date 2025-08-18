# Node.js 入门



> JavaScript 运行时环境



## 1. Node.js 简介



**定义：**[Node.js - MDN Web 文档术语表：Web 相关术语的定义 | MDN](https://developer.mozilla.org/zh-CN/docs/Glossary/Node.js)

<img src="../images/image-20250523153452726.png" alt="image-20250523153452726" style="zoom:50%;" />

**作用：**使用 Node.js 编写服务器端程序

- 编写数据接口，提供网页资源浏览功能等等
- <font color='red'>前端工程化</font>：为后续学习 Vue 和 React 等框架做铺垫



> [!CAUTION]
>
> Node.js 是什么？
> ➢ 基于 Chrome 的 <font color='red'>V8 引擎</font>封装，独立执行 JavaScript 代码的环境



## 2. 什么是前端工程化？



**前端工程化：**开发项目直到上线，过程中集成的所有<font color='red'>工具和技术</font>

Node.js 是前端工程化的基础（因为 Node.js 可以主动读取前端代码内容）

<img src="../images/image-20250523153637978.png" alt="image-20250523153637978" style="zoom:50%;" />



## 3. Node.js 为何能执行 JS？



**首先：**浏览器能执行 JS 代码，依靠的是内核中的 <font color='red'>V8 引擎</font>（C++ 程序）

**其次：**Node.js 是基于 Chrome V8 引擎进行封装（运行环境）

**区别：**都支持 ECMAScript 标准语法，Node.js 有独立的 API

<img src="../images/image-20250523153758155.png" alt="image-20250523153758155" style="zoom:50%;" />

<img src="../images/image-20250523153807119.png" alt="image-20250523153807119" style="zoom:50%;" />

**注意：**<font color='red'>Node.js 环境没有 DOM 和 BOM 等</font>



> [!CAUTION]
>
> Node.js 与浏览器环境的 JS 最大区别？
> ➢ Node.js 环境中<font color='red'>没有 BOM 和 DOM</font>



## 4. Node.js 安装



**要求：**下载 node-v<font color='red'>16.19.0</font>.msi 安装程序（指定版本：兼容 vue-admin-template 模板）

**安装过程：**默认下一步即可

**注释事项：**

1. 安装在<font color='red'>非中文路径</font>下
2. 无需勾选自动安装其他配套软件

**成功验证：**

1. 打开 cmd 终端，输入 node -v 命令查看版本号
2. 如果有显示，则代表安装成功

<img src="../images/image-20250523153937101.png" alt="image-20250523153937101" style="zoom:50%;" />

<img src="../images/image-20250523153919243.png" alt="image-20250523153919243" style="zoom:50%;" />

<img src="../images/image-20250523153927268.png" alt="image-20250523153927268" style="zoom:50%;" />



## 5. 使用 Node.js



**需求：**新建 JS 文件，并编写代码后，在 node 环境下执行

**命令：**在 VSCode 集成终端中，输入 node xxx.js，回车即可执行

<img src="../images/image-20250523154012652.png" alt="image-20250523154012652" style="zoom:50%;" />

<img src="../images/image-20250523154019981.png" alt="image-20250523154019981" style="zoom:50%;" />



## 6. fs 模块 - 读写文件



**模块：**类似插件，封装了<font color='red'>方法/属性</font>

**fs 模块：**封装了与本机文件系统进行交互的，方法/属性

**语法：**

1. <font color='red'>加载</font> fs 模块对象

<img src="../images/image-20250523154220367.png" alt="image-20250523154220367" style="zoom:50%;" />

2. <font color='red'>写入</font>文件内容

<img src="../images/image-20250523154230489.png" alt="image-20250523154230489" style="zoom:50%;" />

3. <font color='red'>读取</font>文件内容

<img src="../images/image-20250525212516495.png" alt="image-20250525212516495" style="zoom:50%;" />

可以使用 data.toString() 方法将 data 数据内容转换成字符串

<img src="../images/image-20250525212626395.png" alt="image-20250525212626395" style="zoom: 67%;" />

<img src="../images/image-20250525212612643.png" alt="image-20250525212612643" style="zoom:50%;" />



## 7. path 模块 - 路径处理



**问题：**Node.js 代码中，相对路径是根据<font color='red'>终端所在路径</font>来查找的，可能无法找到你想要的文件

<img src="../images/image-20250523154337356.png" alt="image-20250523154337356" style="zoom:50%;" />

<img src="../images/image-20250523154344977.png" alt="image-20250523154344977" style="zoom:50%;" />

**建议：**在 Node.js 代码中，使用<font color='red'>绝对路径</font>

**补充：**<font color='red'>__dirname</font> 内置变量（获取当前模块目录-绝对路径）

- windows： D:\备课代码\3-B站课程\03_Node.js与Webpack\03-code\03 
- mac： /Users/xxx/Desktop/备课代码/3-B站课程/03_Node.js与Webpack/03-code/03

**注意：**<font color='red'>path.join() </font>会使用特定于平台的分隔符，作为定界符，将所有给定的路径片段连接在一起

<img src="../images/image-20250523154454226.png" alt="image-20250523154454226" style="zoom:50%;" />

**语法：**

1. 加载 path 模块

<img src="../images/image-20250523154532339.png" alt="image-20250523154532339" style="zoom:50%;" />

2. 使用 path.join 方法，拼接路径

<img src="../images/image-20250523154541106.png" alt="image-20250523154541106" style="zoom:50%;" />



## 8. 案例 - 压缩前端 html



**需求：**把 回车符（\r）和换行符（\n）去掉后，写入到新 html 文件中

**步骤：**

1. <font color='red'>读取</font>源 html 文件内容
2. 正则<font color='red'>替换</font>字符串
3. <font color='red'>写入</font>到新的 html 文件中

<img src="../images/image-20250523154631449.png" alt="image-20250523154631449" style="zoom:50%;" />

<img src="../images/image-20250523154639514.png" alt="image-20250523154639514" style="zoom:50%;" />

<img src="../images/image-20250523154646191.png" alt="image-20250523154646191" style="zoom:50%;" />



## 9. URL 中的端口号



**URL：**统一资源定位符，简称网址，用于访问服务器里的资源

**端口号：**标记服务器里不同功能的<font color='red'>服务程序</font>

**端口号范围：**0-65535 之间的任意整数

<img src="../images/image-20250523154807191.png" alt="image-20250523154807191" style="zoom:50%;" />

**注意：**http 协议，默认访问 <font color='red'>80 </font>端口



## 10. 常见的服务程序



<font color='red'>Web 服务程序：</font>用于提供网上信息浏览功能

注意：0-1023 和一些特定端口号被占用，我们自己编写服务程序请避开使用

<img src="../images/image-20250523154847950.png" alt="image-20250523154847950" style="zoom:50%;" />



## 11. http 模块-创建 Web 服务



**需求：**创建 Web 服务并响应内容给浏览器

**步骤：**

1. 加载 <font color='red'>http 模块</font>，创建 Web 服务对象
2. 监听<font color='red'> request</font> 请求事件，设置响应头和响应体
3. 配置<font color='red'>端口号</font>并<font color='red'>启动</font> Web 服务
4. 浏览器请求 http://localhost:3000 测试

（<font color='red'>localhost</font>：固定代表本机的域名）

<img src="../images/image-20250523155003447.png" alt="image-20250523155003447" style="zoom:50%;" />

<img src="../images/image-20250526104018144.png" alt="image-20250526104018144" style="zoom: 50%;" />



## 12. 案例-浏览时钟



**需求：**基于 Web 服务，开发提供<font color='red'>网页资源</font>的功能

<img src="../images/image-20250523155057704.png" alt="image-20250523155057704" style="zoom:50%;" />

**步骤：**

1. 基于 http 模块，创建 Web 服务
2. 使用<font color='red'> req.url</font> 获取请求<font color='red'>资源路径</font>，判断并<font color='red'>读取 index.html</font> 里字符串内容返回给请求方
3. 其他路径，暂时返回不存在的提示
4. 运行 Web 服务，用浏览器发起请求测试

<img src="../images/image-20250523155126104.png" alt="image-20250523155126104" style="zoom:50%;" />



# Node.js 模块化



## 1. 什么是模块化？



**定义：**[CommonJS 模块 | Node.js API 文档](https://nodejs.cn/api-v18/modules.html#modules-commonjs-modules)

<img src="../images/image-20250525170618114.png" alt="image-20250525170618114" style="zoom:50%;" />

**概念：**项目是由很多个模块文件组成的

**好处：**提高代码复用性，按需加载，<font color='red'>独立作用域</font>

**使用：**需要标准语法<font color='red'>导出</font>和<font color='red'>导入</font>进行使用

<img src="../images/image-20250525170708751.png" alt="image-20250525170708751" style="zoom:50%;" />



## 2. CommonJS 标准



**需求：**定义 utils.js 模块，封装基地址和求数组总和的函数

<img src="../images/image-20250525170741864.png" alt="image-20250525170741864" style="zoom:50%;" />

**使用：**

1. <font color='red'>**导出：**module.exports = {}</font>
2. <font color='red'>**导入：**require('模块名或路径')</font>

<img src="../images/image-20250525170854545.png" alt="image-20250525170854545" style="zoom:50%;" />

<img src="../images/image-20250525170902507.png" alt="image-20250525170902507" style="zoom:50%;" />

**模块名或路径：**

- 内置模块：直接写名字（例如：fs，path，http）
- 自定义模块：写模块文件路径（例如：./utils.js）



## 3. ECMAScript 标准 



### 3.1 默认导出和导入



**需求：**封装并导出基地址和求数组元素和的函数

**默认标准使用：**

1. 导出：<font color='red'>export default {}</font>
2. 导入：<font color='red'>import 变量名 from '模块名或路径</font>

<img src="../images/image-20250525170946906.png" alt="image-20250525170946906" style="zoom:50%;" />

<img src="../images/image-20250525171011483.png" alt="image-20250525171011483" style="zoom:50%;" />

注意：Node.js 默认支持 CommonJS 标准语法

如需使用 ECMAScript 标准语法，在运行模块所在文件夹新建 package.json 文件，并设置 { "type" : "module" }

<img src="../images/image-20250525171029782.png" alt="image-20250525171029782" style="zoom:50%;" />



### 3.2 命名导出和导入



**需求：**封装并导出基地址和求数组元素和的函数

**命名标准使用：**

1. 导出：<font color='red'>export 修饰定义语句</font>
2. 导入：import { 同名变量 } from '模块名或路径‘

<img src="../images/image-20250525171215157.png" alt="image-20250525171215157" style="zoom:50%;" />

<img src="../images/image-20250525171222242.png" alt="image-20250525171222242" style="zoom:50%;" />

**如何选择：**

- <font color='red'>按需</font>加载，使用<font color='red'>命名</font>导出和导入
- <font color='red'>全部</font>加载，使用<font color='red'>默认</font>导出和导入



## 4. 包的概念



**包：**将<font color='red'>模块，代码，其他资料</font>聚合成一个文件夹

**包分类：**

- 项目包：主要用于编写项目和业务逻辑
- 软件包：<font color='red'>封装工具和方法</font>进行使用

**要求：**根目录中，必须有 package.json 文件（记录包的清单信息）

<img src="../images/image-20250525171414305.png" alt="image-20250525171414305" style="zoom:50%;" />

**注意：**导入软件包时，引入的默认是 index.js 模块文件 / main 属性指定的模块文件

<img src="../images/image-20250525171402618.png" alt="image-20250525171402618" style="zoom:50%;" />

**需求：**封装数组求和函数的模块，判断用户名和密码长度函数的模块，形成成一个<font color='red'>软件包</font>



## 5. npm 



### 5.1 软件包管理器



**定义：[Node.js 中文网](https://dev.nodejs.cn/learn/an-introduction-to-the-npm-package-manager#npm-简介)**

<img src="../images/image-20250525171500852.png" alt="image-20250525171500852" style="zoom:50%;" />

**使用：**

1. 初始化清单文件 ：npm init -y（得到 package.json 文件，有则略过此命令）
2. 下载软件包 ：<font color='red'>npm i 软件包名称</font>
3. 使用软件包



**需求：**使用 dayjs 软件包，来格式化日期时间

**图解：**

<img src="../images/image-20250525171549634.png" alt="image-20250525171549634" style="zoom:50%;" />



### 5.2 安装所有依赖



**问题：**项目中不包含 node_modules，能否正常运行？

**答案：**不能，缺少依赖的本地软件包

**原因：**因为，自己用 npm 下载依赖比磁盘传递拷贝要快得多

**解决：**项目终端输入命令：<font color='red'>npm i</font>

下载 package.json 中记录的所有软件包

<img src="../images/image-20250525171923612.png" alt="image-20250525171923612" style="zoom:50%;" />

<img src="../images/image-20250525171932048.png" alt="image-20250525171932048" style="zoom:50%;" />



### 5.3 全局软件包 nodemon



**软件包区别：**

- 本地软件包：<font color='red'>当前项目</font>内使用，封装<font color='red'>属性和方法</font>，存在于 node_modules 
- 全局软件包：<font color='red'>本机</font>所有项目使用，封装<font color='red'>命令和工具</font>，存在于系统设置的位置

**nodemon 作用：**替代 node 命令，实时检测代码更改，自动重启程序

**使用：**

1. 安装：npm i nodemon -g（-g 代表安装到全局环境中）
2. 运行：nodemon 待执行的目标 js 文件

需求：启动准备好的项目，修改代码保存后，观察自动重启应用程序



# Node.js 总结



**Node.js 模块化：**

概念：每个文件当做一个模块，独立作用域，按需加载

使用：采用特定的标准语法导出和导入进行使用



<img src="../images/image-20250525172128294.png" alt="image-20250525172128294" style="zoom:50%;" /><img src="../images/image-20250525172134246.png" alt="image-20250525172134246" style="zoom:50%;" />



**CommonJS 标准：**一般应用在 Node.js 项目环境中

**ECMAScript 标准：**一般应用在前端工程化项目中



**Node.js 包：**

**概念：**把块文件，代码文件，其他资料聚合成一个文件夹

**项目包：**编写项目需求和<font color='red'>业务逻辑</font>的文件夹

<img src="../images/image-20250525172252861.png" alt="image-20250525172252861" style="zoom:50%;" />

**软件包：**<font color='red'>封装工具和方法</font>进行使用的文件夹（一般使用 npm 管理）

- 本地软件包：作用在<font color='red'>当前</font>项目，一般封装的<font color='red'>属性/方法</font>，供项目调用编写业务需求
- 全局软件包：作用在<font color='red'>所有</font>项目，一般封装的<font color='red'>命令/工具</font>，支撑项目运行

<img src="../images/image-20250525172300293.png" alt="image-20250525172300293" style="zoom:50%;" />



**常用命令：**

|        功能         |                    命令                    |
| :-----------------: | :----------------------------------------: |
|    执行 js 文件     |     <font color='red'>node xxx</font>      |
| 初始化 package.json |    <font color='red'>npm init -y</font>    |
|   下载本地软件包    |  <font color='red'>npm i 软件包名</font>   |
|   下载全局软件包    | <font color='red'>npm i 软件包名 -g</font> |
|     删除软件包      | <font color='red'>npm uni 软件包名</font>  |

