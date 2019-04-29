Node.js是基于Chrome V8 引擎的js运行环境

Node.js使用了一个事件驱动、非阻塞式I/O的模型，时期清凉又高效

工具： 淘宝镜像  www.npmjs.com

包管理器：

​	cnpm 

​	npm 

​	yarn

nvm  Node版本切换

​	nvm list 查看版本

​	nvm use 8.9.2 切换版本

​	下载nvm-setup.zip  一路下一步  卸载桌面助手

​	nvm安装路径

![1556244482185](C:\Users\shinelon\AppData\Local\Temp\1556244482185.png)



​	获取当前目录所有内容： dir /w

​	linex: ls 查看目录

## vs code 里面如何切换自定义终端？

浏览器有两个渲染机制： html + js

cls清屏  浏览器 clear() 清屏

## 浏览器 vs node

异：

​	1.node 里面没有BOM  DOM

​	2.node 多了没有自带的API

同：

​	1.都是Chrome v8

​	2.都支持js

​	3.都支持ECMA  script

## 3.需求：sum这个方法，我想三个参数，计算三个参数值

1.Node.js  命令行用起来不方便

2.解决：我们使用文件  .js

## Node.js 命令行退出

1.two times ctrl+c

## Node.js文件运行

node 文件名称 （后缀可以不要） tab自动补全

键盘上下键回退前进命令

## 自动监听（自动更新，自动监听）Node.js文件的更新和变化（工具  nodemon  supervisor）

使用淘宝镜像

1.工具安装

​	cnpm i nodemon -g  (i ==> install g==> global)  推荐

​	cnpm i supervisor -g

2.使用：

​	nodemon 文件名称  // 自动监听

​	supervisor 文件名称

3.注意事项

​	问题：	supervisor 会出现死循环  

​	分析：内容一直在改变

​	解决：vs code 开了自动保存

### 使用不同Node.js

![1556245925845](C:\Users\shinelon\AppData\Local\Temp\1556245925845.png)

​	nvm  查看命令

​	nvm install latest 安装最新版本

​	nvm list 查看所有已经下载版本

​	nvm use 10.14.0 进入版本

​	node -v 查看版本

##nvm使用

1.安装：

​	nvm install version

​	nvm install 10.15.3  安装10.15.3版本 || nvm install latest(最新版本)

2.切换Node.js版本

​	nvm user version

3.查看当前电脑Node.js所有版本

​	nvm list

​	10.15.3版本号第二个参数 单数是测试版，双数是稳定版

​	LTS也是稳定版  Current是最新版（不稳定）

## 前端模块化（面试题）

​	1.CMD (sea.js 工具)

​	2.AMD (require.js)

​	3.Common.js   :   

​		1.require   导入其他模块的成员的

​		2.export    向外暴露成员

​		3.module   表示一个模块

​	4.es6模块化



​	CMD 和 AMD

​		define 定义模块

* #####Node.js 中使用了Common.js规范）（三类）

    		1.内置的（核心模块）：由Node官方提供的好用的模块，安装Node自带的
    			使用：require('核心模块标识符')
    			
    		2.第三方的：一些非官方提供的模块，叫做第三方模块；并不在我们的计算机上，需要使用，必须去NPM的网站上搜索使用
    			使用：先从npm 官网上下载指定的第三方模块
    			使用require('第三方模块的名称标识符')来导入这个模块
    			根据第三方模块的官方文档，尝试使用
    	
    		3.自定义的：
    			1.什么事用户模式：程序猿自己写的js文件，就叫做用户自定义模块
    			2.使用：require('路径标识符')

Node.js内置了很多的模块

​	fs(文件系统)

​	path(磁盘路径)

​	http(通信)

使用：

​	1.导入

​		const 变量名称 = require('模块名称')

​	2.使用模块的api

​		const path = require('path')

​		path.resolve(__dirname)  //当前目录文件夹

​	// 需求： 返回上一级？

​		path.resolve(__dirname, '../')  // 返回上一级

	#### 暴露模块

​	1.global.a = a

​	2.exports.a = a   发送   （推荐， 不污染全局） 暴露

​	require('./m1.js')  接收  导入

​	如果在一个组件中，传多个值，那么接收方，接受的就是一个对象

​	module.exports === exports  // true

​	exports和module.exports传递的是同一个对象

​	3.module.exports.a = 10

​	exports.b = 10   {10,10}

	##### 在一个模块中，默认情况下，module.exports和exports是指向同一个空对象的

##### 在同一个模块中，在向外暴露成员的时候，永远以module.exports指向的对象为准

 



​		

	#### 第三方模块使用：https: // www.npmjs.com

1.安装：

​	1.初始化生成 package.json

​	2.安装对应的包

​		npm i request -g/-D/-S

​		名词说明：

​			-g  -global  全局

​			-D / --save-dev  开发环境

​			-S / -save  生产环境

2.导入

​	request: 用来做处理请求的 

​	npm i request -S

3.使用

​	去看文档（www.npmjs.com）

​	const request = require('request')

​	request('接口', (err, responsr, body) = > {

​		console.log('=======================')

​		console.log('error', error)

​		console.log('response', response)

​		console.log('body', body)  // json类型的字符串

​		console.log('body', JSON.parse(body))  // 解析

​		console.log('=======================')

​	})

## 前端的环境

1.开发环境 ： 真在做

2.生产环境：做好再用

3.测试环境：测试在上线环境是否可用

4.预发布环境：公司内部测试

5.上线环境：

## 问题：Node.js中请求数据， 需要跨域吗？

​	跨域：

​		安全策略

​		同源策略

​	1.说明：

​		1.为什么会出现跨域

​			开发中会出现不同的域名和端口等出现？我们需要去获取他们的内容

​		2.浏览器如何组织跨域

​			浏览器具有安全策略  ---》同源策略实现

​		3.夸域的范围是？

​			跨域针对的是浏览器  

​			后端不需要跨域

## 问题：为什么要有 pack.json?

​	删除：	rm -rf node_modules/

​	即使没有node_modules也可以下载  npm i

## Node.js自定义模块步骤

​	1.定义

​		对象  函数  字符串  ...

​	2.导出

​		module.export || exports

​	3.使用

​		const 变量名称 = require(‘模块名称’)

1.定义

##### age.js

​	const age = {

​		name: 'y',

​		age: 16

​	}

2.导出

//  module.exports = age

module.exports =  {

​	age: age.age,

​	name: age.name

}

####exports是module的一个辅助工具

// exports.age = age

3.使用

##### index.js![1556250080665](C:\Users\shinelon\AppData\Local\Temp\1556250080665.png)



​	4.扩展

​		1.需求： 安全性考虑  封装一下

## 自定义模块发布

自定义发布一个包（带有一定功能），别人可以随意下载，使用

1.包先做好

2.在https:// npmjs.com   这个网站注册账号（github账号也行）

3.操作流程：

​	1.npm 

​	![1556250914057](C:\Users\shinelon\AppData\Local\Temp\1556250914057.png)





总结：	

​	1.使用Node.js实现一个web服务器

​	2.Node.js中模块的api很多时候可以连缀（链式调用）

​	3.http

​		1.createServer  穿件一个web静态服务器

​		2.listen  是用来监听当前服务器

​		3.名词解释

​			1.port  端口

​			2.hostname：域名

​			3.request  请求，Node.js请求谁

​			4.response  回应

​			5.data   数据

​			6.encoding   编码方式   默认 utf8

​		4. write(data, encoding)   给前台发送一个内容

const http = require('http');

const prot = 8090;

const hostname = 'localhost'  // 127.0.0.1



格式：http.createServer(callback).listen(prot, hostname, callback)

http.createServer(function (request, response) {

​	response.write('yanyabing')

}).listen(prot, hostname, function () {

​	

})



1.mkdir  文件名  	创建文件夹

# linux

1.mkdir  创建文件名

2. vim 简写 vi  创建文件的

3. rm -rf 文件名称  删除

4. 递归删除

   find  ./  -name  '文件名称'  -print  -exec  rm  -rf  {}  \;

   举例：find  ./  -name  'node_modules'  -print  -exec  rm  -rf  {}  \;

	 ###mstsc	可以打开远程连接

## 什么是包？ --》 packages

1.包可以看做是模块，代码，和其他资源组合起来形成的一个独立作用域

2.包是在模块基础上，更深一步的抽象，目的性：方便分发推广基于CommonJS规范实现的应用程序或类

### 规范的包结构

1.**包要以一个单独的目录存在**

2.**`package.json`必须在包的顶层目录下**

3.**`package.json`文件必须符合JSON格式，并且必须包含如下三个属性：`name` ,`version`,`main`

​	name: 包的名字

​	version: 包的版本号

​	表示包的入口文件

4.二进制文件应该在bin目录下

5.javascript代码应该在lib目录下

6.文档应该在doc目录下

7.单元测试应该在test目录下

8.Node.js对包要求并没有那么严格，只要顶层目录下有`package.json`，并**符合基本代码规范**即可

#### 自定义包

![1556276502352](C:\Users\shinelon\AppData\Local\Temp\1556276502352.png)

### 包描述文件

```
name: 包的名称，必须是唯一
description: 包的简要说明
version: 符合语义化版本识别规范的版本字符串
keywords: 关键字数据，通常用于搜索
maintainers: 维护者数组，每个元素要包含name、email、web、可选字段

```

##npm

npm升级：	   npm i npm -g

###npm的两层含义

1.npm 是一个第三方模块的托管网站，指的是`https://www.npmJS.com`

2.npm 是Node的包管理工具，，在我们安装Node的时候就已经顺带安装了NPM这个管理工具

### 安装和卸载全局包

1.什么是全局包：`npm install 包名 -g` 方式安装的包，都安装在全局；一般全局的安装目录是`C:\User\自己的用户文件夹\AppData\Roaming\npm`

2.带大家演示如何安装一个全局包：`npm install i5ting_toc -g` 表示全局安装包的意思

i5ting_toc -f  .\day1.md -o加-o自动打开浏览器

3.注意：一般，只有一些工具，才有全局安装的必要性

4.如果要全局卸载某个包，比如要卸载`i5ting_toc`了，直接运行`npm uninstall i5ting_toc -g`就可以全局卸载这个包了

#### 全局包，只需要安装一次终生有效，只要不出错

#### npm安装包

+ npm 基本操作

  + npm init -y 初始化

  + npm i jquery --save  安装jquery包
+ 安装和卸载本地包

  + 1.什么事本地的包：跟着项目安装的包，叫做本地包
  + 2.日过拿到一个空项目，必须县初始化一个`package.json`的配置文件，`npm init`或者`npm init -y`
  + 3.运行`npm i 包名 --save`去安装指定的包
  + 4.如果大家使用的是npm 5.x的版本，可以不指定`--save`命令，如果用的是npm 3.x的版本，则需要写入`--save`
  + 5.package-lock.json可以加快下次装包速度，他的作用是用来记录曾经装包地址，方便下次直接下载
    + 卸载jquery  `npm uninstall jquery --save`
    + 下载`npm i jquery -S`
    + 安装模板引擎
      + `npm i art-template -S`
+ 简写说明
  + `-S`  ->  `--save`
  + `-D`  ->  `--save-dev`
  + `i`   ->   `install`
+ 下载须知
  + `npm i nrm -g`  (注意：只要是工具，一般都是全局 -g 安装)
  + 

## nrm

+ nrm 执行命令
  + `nrm ls`  查看所有可用的服务器列表
  + `nrm  use 服务器名称` 来切换下载包时候的服务器地址

## 构建web应用（服务器）
Apache 是一个PHP的服务器，当我们把做好的网站，丢到 WWW 目录下，就能够使用 IP地址 + 端口号 访问我们的网站了；
+ IP地址的作用，是为了表示当前网络中这台计算机唯一身份的；
+ 端口号：端口号和应用程序有关联，每一个应用程序，只能独占一个端口号，不能说多个应用程序公用一个端口；
  疑问：Node中，有没有类似于 Apache 这样的服务器软件，来提供对应的网站服务呢？注意：Node中，并没有现成的 类似于 Apache 的服务器软件，如果我们想通过Node，来对外托管一个网站的话，需要自己手写一个 类似于 Apache 的服务器；
### BS 交互模型
+ HTTP 协议是基于 `请求 - 处理 - 响应` 通信模型的
	 B/S: 表示  Browser/Server		C/S  Client / Server
+ 1.什么事服务器：网络节点中，专门对外提供资源服务的一台电脑
+ 2.什么是客户端：在网络节点中，专门用来小号或呈现服务器中返回的数据的电脑
+ 3.什么事静态资源：像.js  , .css, .jpg, .html ;  所谓的静态资源， 就是无需数据数据交互，服务器直接把资源读取，冰箱应该客户端就完事了
+ 4.什么是动态资源：当一些资源，服务器上并没有现成的，需要现在服务器端，做一层处理，然后把处理的结果再返回客户端，这样的资源，叫做动态资源
+ 5.HTTP协议的通信模块：`请求 - 处理 - 响应`的过程

### 实现静态资源服务器

+ 1.后端路由的本质
  + 重点理解URL（统一资源定位符）的本质

### 结合模板引擎实现动态资源服务器

### 静态资源请求路径问题

+ 1.在浏览器的严重，只要是地址栏中的地址，浏览器永远把最后一个`/`后面的符号，认为是文件名
+ 2.对于服务器来说，客户端请求的URL资源路径只是一个 **标识符** 而已，URL不一定非要对应实际的物理磁盘路径！
+ 3.一定要区分html中书写的路径标识符`../`   `./`   和  `/`   **在浏览器中**代表含义!
  + `/`表示，直接从端口号后面，开始资源请求
  + `./`表示，在发起资源请求之前，浏览器需要先把URL地址， 和资源路径做一层拼接
  + `../`表示，在发起资源请求之前，浏览器需要先把URL地址，和资源路径做一层拼接



## 使用  `nodemon`  工具来自动重启web服务器

+ 这个工具的作用：能够实时监听web服务器中，代码的改变，只要代码被修改并保存了，则nodemon工具，会自动重新启动web服务器
+ 运行**`npm i nodemon -g`** 就能够自安全局环境中，安装这个工具了
+ 当安装完毕`nodemon`之后，就可以使用**`nodemon 就执行的js文件路径`**来运行js文件
+ 今后在开发Web项目的时候，推荐使用**nodemon**来执行web服务器



## Node中的Web快速开发框架 - Express

+ ### Express 简介

  + Express 是一个简洁而灵活的 node.js Web应用框架, 提供了一系列强大特性帮助你创建各种 Web 应用，和丰富的 HTTP 工具。
  + 使用 Express 可以快速地搭建一个完整功能的网站。
  + Express 框架核心特性
    + 可以设置中间件来响应HTTP请求
    + 定义了路由表用于执行不同的HTTP请求动作
    + 可以通过向模板传递参数来动态渲染HTML页面

+ ### express 框架的安装和基本使用

    + 直接运行  **`npm install express --save`**  就可以安装Express框架了

+ ### expross的运用以方法

  + ##### 1.获取express的包：const express = require('express')

  + #####调用express()  可以得到一个 express 服务器

  + #####2.const app = express()

    + app.get  // 发送get请求

      + ```
        1.  app.get('/index.html', (req, res) => { res.send('这是Get请求') })
        2.  app.get('/index.html', (req, res) => { res.sendFile(path.join(__dirname,'./view/index.html')) })
        ```

    + app.post  // 发送post请求

      + ```
        app.post('/api/postinfo', (req, res) => { res.send('这是Post请求') })
        ```

    + app.all  // 

    + app.listen  // 启动服务器

      + ```
        app.listen(3000, () => { console.log('express server running at http://127.0.0.1:3000') })
        ```

  + #####res

    + res.send  // 发送字符串
    + res.sendFile  // 发送具体的文件

+ ###定义什么是Express:

  - 给予Node.js 后端 js平台之上，开发出来的一套Web开发框架
  - Express中，给予原生Node的特性，做进一步的封装，提供了一些更加好用的方法，来提高Web开发的体验
  - Express中，并没有覆盖或者删除原生的http模块方法

+ ###使用express 快速托管静态资源

  + 1.如果我们网站中，有很多静态资源需要被外界访问，此时，使用 res.sendFile 就有点力不从心了，这时候express框架，为我们提供了一个内置的（中间件）  **`express.static(静态资源目录)`**  ，来快速托管指定目录下的所有静态资源文件

  + 2.用法：  **`app.use(express.static('public'))`**  
    + 其中，  **`express.static`**  是一个express的内置中间件

    + **`app.use()`**  方法，是专门用来注册中间件

    + ```
      app.use(express.static('./views(需要用到的静态资源目录)'))
      
      // 如果在托管静态资源的时候，直接使用了 app.use(express.static('./assets'))方式，则访问assets目录下资源的时候，路径中，不能出现/assets
      // 但是，我们为了能有路径的只能提示，推荐大家，在第一个参数的位置，手动挂载一个 路径标识符 ，这就表示，将来托管的静态资源文件，在访问的时候，路径中，必须要包含我们为其挂在的那个 路径标识符
      app.use('/assets', express.static('./assets'))
      ```

  + 3.当使用第二步中的方法，把指定目录托管伪静态资源目录之后，那么，这一层**`被托管的目录` **，不应该出现在资源访问的URL地址中

  + 4.在一个Web项目中，我们可以多次调用**`app.use(express.static)`**

  + 5.再多次调用express.static的时候，如果文件名称有重复的，则以先注册的中间件为主

  + 6.如果项目要部署了，推荐大家配置一个叫做  **`compression`**  的中间件，它能够开启服务器的Gzip压缩功能

    + ```
      // 
      const express = require('express)
      // 获取压缩的包
      const compression = require('compression)
      const server = express()
      // 注册资源压缩的中间件
      server.use(compression())
      // 托管静态资源目录
      server.use(express.static('./assets'))
      // 启动服务器
      server.listen(80, () => {
          console.log('express server running at http://127.0.0.1:80')
      })
      ```

+ ### 为express 框架配置模块引擎渲染动态页面

  + 1. 安装ejs模块引擎  **`npm i ejs -S`**  

    2. 使用**`app.set()`**  配置默认的模板引擎**`app.set('view engine（必须这么写）', 'ejs')`**

    3. 使用**`app.set()`**配置默认模板页面的存放路径**`app.set('views', './views')`**

    4. 使用**`res.render()`**来渲染模板页面**`res.render('index.ejs', { 要渲染的数据对象 })`**，注意，模板页面的**后缀名**，可以**省略不写**

    5. ```
       const express = require('express')
       const app = express()
       const path = require('path')
       app.set('view engine', 'ejs')  // 配置默认的模板引擎
       app.set('views', './views')  // 注意：第一个参数，是固定写法，第二个参数，是模板页面的存放地址
       app.get('/', (req, res) => {
           // res.sendFile 只能 提供静态文件，无法渲染动态页面
           // res.sendFile(path.join(__dirname, './views.index2.html'))
           // res.render()函数，是express框架独有的，其中
           // 参数一：是要渲染的页面名称
           // 参数二：是要渲染的数据对象
           // 注意：默认情况下，我们无法直接使用res.render函数来渲染动态页面，因为express并没有为我们提供默认的模板引擎
           // 所以，在调用res.render()函数之前，我们要先人为的指定使用哪个模板引擎来渲染页面
       // res.render('index.ejs', person)
       res.render('index', person)  // 也可以省略.ejs
       })
       ```

    ![1556353348029](C:\Users\shinelon\AppData\Local\Temp\1556353348029.png)

+ ### 使用express框架中提供的路由来分发请求

  + 1. 什么叫做路由：前端请求的URL地址，都要对应一个后端的处理函数u，那么 这种URL地址到处理函数之间的对应关系，就叫做后端路由

    2. 在Express中，路由主要负责分发请求处理的

    3. 在Express中，如何定义并使用路由呢
    ```
       // 封装单独的  router.js  路由模块文件
       const express = require('express)
       // 创建路由对象
       const router = express.Router()
       
       router.get('/', (req, res) => {})
       router.get('/movie', (req, res) => {})
       router.get('/about', (req. res) => {})
       
       // 导出路由对象
       module.exports = router
    ```

    4. exrepss创建的app服务器， 如何使用路由模块呢

    ```
    // 导入自己的路由模块
    const router = require('./router.js')
    // 使用 app.use() 来注册路由
    // 将路由对象，注册到app服务器上，这样每当有请求过来，就可以调用路由模块，来分发处理请求了 
    app.use(router)
    ```




## 中间件

+ 中间件介绍
  + 1.中间件是一个函数
  + 2.中间件这个函数，是一个路由处理函数
  + 3.中间件这个函数，不但是一个路由处理函数，而且，在参数列表中，还有一个重要的参数叫做`next`
  + 4.这个**next**是一个函数，因此，将来，我们可以在中间件中，调用这个**next()**函数
  + 5.中间件的表现形式：只要这个函数的形参列表中，有一个next函数，他就是一个中间件
+ 中间件的作用：
  + 中间件表示没一个处理环节，只负责单独的处理，每当上一个中间件处理完毕后，必须把处理的原材料，交给下一个中间件来继续处理



## unix和linux	

+ unix:  // mux笔记本   // 操作系统

+ linux：// 
  + mkdir 创建文件夹
  + vim 简写 vi 创建文件的
  + rm -rf 文件名称  删除
  + 递归删除
    + find ./ -name  '文件名称'('node_modules')  -print -exec rm -rf {} \;
  + cat 文件名称  查看某个文件的内容

  + 前端渲染 vs 后端渲染
    + 前端拿到数据之后，前端来循环渲染数据

    + 后端渲染，后端来进行渲染（express）

    + 浏览器 -》 开发者工具  -》 network -》

      + ####headers头部报文

        + General（请求的状态信息）
        + Response Headers（响应头的设置）
          + ACAO允许跨域
          + ACAC跨域通行证
        + Request Headers（请求头的设置）
        + Query String Parameters（携带参数）
        + form data（表单提交来的参数）

    + 后端渲染找 Network -> Doc

    +  Network -> WS聊天通信，网络直播经常用

    + 前端渲染找 Network -> XHR

+ 文件操作

  + ![1556440306553](C:\Users\shinelon\AppData\Local\Temp\1556440306553.png)

## 后端爬虫
​	数据抓取 -》 数据清洗 -》 数据格式整理 -》 发送前台（web服务器）

+ 反爬虫
  + 数据清洗的时候做，数据中用一个其他类型格式的数据



## events模块

+ Emitter.prototype  继承过来了  on  emit

## fs/zlib/steam

## Node.js原生路由

## 前端异步流程控制工具

+ promise
+ generator函数
+ Node.js 中 nextTick 和 setImmediate
+ async库
+ Async-await

## npm script (npm 脚本)

+ package.json  中的代码
+ Npm 脚本将相当于电器说明书
+ npm 脚本运行 npm run 
+ npm 脚本可以简写，但是只有特定几个
  +  npm start -> npm run start
  + npm stop -> npm run stop
  + npm test -> npm run test
  + npm restart -> npm run stop & npm run start

## express

+ express介绍：

  + 构建后端项目的一个框架

+ 构建后段项目

  + 安装生成器

    + npm i express-generator -g

  + 使用

    + express options 项目名称

  + 创建项目

    + 举例：express 04-express-project
      + express -e project

  + 目录内容

    + bin           项目的配置文件（比如：port（端口）） 
      + www      使用http模块创建了一个web服务器
    + public      静态资源文件夹（ html  css  images  js ）
    + routes     路由
    + views       后端模板文件夹
    + app.js      整个项目的入口文件
    + package.json    整个项目的依赖包配置文件（说明书）

  + 项目的启动

    + 1.进入项目
      + cd项目名称
    + 2.安装项目依赖
      + npm install
    + 3.项目启动
      + npm start

  + 建议：

    + 看到一个项目，首先看一个项目的说明书(package.json)

  + package.json:

    + dependencies   // 生产换境

  + 看一个环境流程

    + 依赖包
    + npm脚本 --》 项目启动命令  --》  配置文件（bin->www）

  + express 中间件

    + 中间件的概念：

      + 具有特定功能的插件

      + ```
        中间件（Middleware） 是一个函数，它可以访问请求对象（request object (req)）, 响应对象（response object (res)）, 和 web 应用中处于请求-响应循环流程中的中间件，一般被命名为 next 的变量。
           中间件的功能包括：
             * 
           执行任何代码。
             * 
           修改请求和响应对象。
             * 
           终结请求-响应循环。
             * 
           调用堆栈中的下一个中间件。
         中间件包含三个部分（形式参数）
           request : 请求
           response： 响应
           next： 请求和响应流程中的中间件， 用next变量表示
        
        ```

      + 中间件包含三个部分（形式参数）

        + request:  请求
        + response:  响应
        + next:  请求和响应流程中间件，用next变量表示

    + express中提供了：

      + 1.应用级中间件
        + app对象  --》 use()  和  -->  method()
        + 应用级中间件就是一个具有特定功能性的函数，这个函数需要绑定在app对象身上，通过app.use() || app.method()来调用
      + 路由中间件
        + 
      + 错误中间件
        + 

    + app对象

      + const app = express()
      + 使用
        + 1.app.use()
          + 调用 中间件（函数）
        + 2.app.method()  // 处理http请求的
      + 前端请求方式很多的：
        + get
        + post
        + delete // 删除请求
        + put // 添加请求
        + all  // 所有的

+ ## express已经不常用了，koa非常用

  + koa是express超集（进阶版）

## 杭州：函数中间件封装

##utils:  工具和插件

## Node.js渲染模板

+ 1.ejs
+ 2.pug(曾用名：jade) 语法功能很强大
+ 3.art-template (纯后端模板)

## 前后端分离

+ Tomcat+Ngnix，可以有效的进行解耦

## koa（扩展知识，建议学习）

+ koa是express超集（进阶版）

## 前后端分离和耦合概念介绍

+ 面向过程 -》 面向对象 -》面向服务
+ 耦合度高：
  + 代表前端后端基本不分离，后端要干两个人（前端和后端）的事，工作量更大了
+ 耦合度低：
  + 表示前后端分离，各司其职，这个效率比较高

## 数据库  Node.js  mongodb(bson json的超集)

+ 分类：
  + 关系型数据库：  MySql
  + 非关系型数据库：  MongoDB

## MongoDB安装

+ 环境变量设置
  + ![1556522761615](C:\Users\shinelon\AppData\Local\Temp\1556522761615.png)
+ 系统服务添加有问题

​	

# MongoDB安装

1. 环境变量设置

2. 系统服务添加有问题

3. 安装
   系统不太支持高版本、 降版本 3.2  3.4 

   写在mongodb时候， 记得删除之前创建好的文件夹

4. 每次启动
   最好先  
     net start MongoDB
   在： 
     mongo

# 问题？MongodDB

1. MongoDB的存储数据的形式bson

  数据库功能是用来存储数据的。
  数据库分为关系系数据库和非关系型数据库(nosql)
  关系型数据库是由表和表之间的关系组成的，nosql是由集合组成的，集合下面是很多的文档。
  非关系型数据库文件存储格式为BSON（一种JSON的扩展）。



## MongoDB优点

+ 他的特点是高性能、易部署、易使用，存储数据非常方便，主要功能：
  + 想象聚合存储，易存储对象类型的数据
  + 模式自由
  + 支持动态查询
  + 支持完全索引，包含内部对象
  + 支持查询
  + 支持复制和故障恢复
  + 使用高效的二进制数据存储，包括大型对象（如视频等）
  + 自动处理碎片，一直吃云计算层次的扩展性
  + 支持RUBY，PYTHON，JAVA，C++，PHP等多种语言
  + 支持存储格式为BSON（一种JSON的扩展）

## BSON

+ BSON是一种类似[json](http://baike.baidu.com/view/136475.htm)的二进制形式的存储格式，简称Binary JSON，它和JSON一样，支持内嵌的**文档对象**和**数组对象**，但是**BSON有JSON没有的一些数据类型，**如Date和BinData类型。

   

  ​    BSON可以做为网络数据交换的一种存储形式，这个有点类似于Google的Protocol Buffer，但是BSON是一种schema-less的存储形式，它的优点是灵活性高，但它的缺点是空间利用率不是很理想。

  BSON有三个特点：轻量性、可遍历性、高效性。

   

  后面大家会看到我们存在数据库里面的全部都是bson格式的数据。

## 非关系型数据库与关系型数据库区别

+ 非关系型数据库的优势：

  \1. 性能

  NOSQL是基于键值对的，可以想象成表中的主键和值的对应关系，而且不需要经过SQL层的解析，所以性能非常高。

  \2. 可扩展性

  同样也是因为基于键值对，数据之间没有耦合性，所以非常容易水平扩展。

  关系型数据库的优势：

  \1. 复杂查询

  可以用SQL语句方便的在多个表之间做非常复杂的数据查询。

  \2. 事务支持

  使得对于安全性能很高的数据访问要求得以实现。



## linux命令

+ cls 清屏



# MongoDB操作命令

1. MongoDB连接地址： mongodb://127.0.0.1:27017

2. use db_name
   举例： 
     创建： 我们的数据库中没有 你要切换的数据库， 那么即为创建
     切换： 数据库已经存在， 我们从一个数据库切换到另一个数据库

3. show dbs
   将我们本地的所有数据库列出来

4. db/db.getName()
   查看当前使用的数据库

5. MongoDB
   数据库 -》 集合 -》 文档
   针对数据库（database）的操作

   1. help
   2. use db_name            
   3. db||db.getName()
   4. db.states()
   5. db.dropDatabase() 
   6. show dbs
   7. db.versions()
   8. db.getMongo()

   针对集合(collections)的操作

     （1）创建一个集合
         db.createCollection("collName", {size: 20, capped: true, max: 100});
         db.collName.isCapped(); //判断集合是否为定容量
     （2）得到指定名称的集合
        db.getCollection("account");
     （3）得到当前db的所有集合
         db.getCollectionNames();
     （4）显示当前db所有集合的状态
         db.printCollectionStats()

   针对文档（docuemnt）的操作

   1. 添加

      1. db.coll_name.save({})         推荐
      2. db.coll_name.insertOne({})
      3. db.coll_name.insert({})

   2. 查询
      db.coll_name.find(arg1,arg2) 所有的
      参数解释：
        arg1 表示的是匹配条件
        arg2 表示将来输出的内容匹配   0 表示不要， 1表示要

        举例： 
          db.movies.find({year:'1993'},{_id:0,title:1})

      升序
        举例： 
            db.movies.find({year:'1993'},{_id:0,title:1}).sort({year:1})

      降序
        举例
            db.movies.find({year:'1993'},{_id:0,title:1}).sort({year:-1})

      截取  某条以前 limit
           db.movies.find({year:'1993'},{_id:0,title:1}).limit(5)
      截取  某条以后 skip

      优先级： 
        sort>skip>limit

      $or表示或者， 可以匹配多个条件
        db.teachers.find({$or:[{age:10},{age:40}]})

      findOne() 第一条数据

        db.teachers.findOne()

      count() 计数

        举例： 
          db.movies.find({year: {$gt:"1993"}},{_id:0,title:1,year:1}).count()  //16

   3. 删除
      db.coll_name.remove({})

   4. 修改
      db.coll_name.update(arg1,arg2,arg3,arg4)
      参数解释： 

      1. arg1: 匹配条件
      2. arg2: 修改的具体内容
      3. arg3:  false / true      匹配几条  false  一条   true  多条
      4. arg4:  false / true      修改几条  false  一条   true 多条
         $set 直接设置
           db.teachers.update({age:120},{$inc: {age: 80}},false,true)
         $inc 在当前基础上增加多少
           db.teachers.update({age:120},{$inc: {age: 80}},false,true)
























​       









​	

​		





