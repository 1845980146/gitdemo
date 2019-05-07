## 开发须知

+ ###1.前端工作规范：

  + ####目录构建的规范：

    + 1简洁
      + 比如：src 源代码  img 图片资源  js javascript脚本  dep 第三方依赖包
    + 2.不是用复数
      + 比如：不适用	imgs	docs

  + 根目录（root）结构俺只能划分

    + 比如
      + 1.src源代码（逻辑）
      + 2.doc文档
      + 3.dep 第三方依赖包
      + 4.test 测试

  + 根据业务逻辑进行文件夹的划分

    + src  源代码
      + common 公共资源
        + img
          + logo.png
          + sprites.png
        + css
          + reset.css
        + js
          + conf.js  项目的配置文件
      + public/static 静态资源
        + js
        + css
        + html/tpl
          + index.html
          + shopcar.html
        + img
      + component  组件
        + home主页
        + shopcar购物车
        + login 登录
        + register 注册
        + user 用户
        + list 列表
        + detail 详情页
      + views/tpl  项目模板  tpl 是template的缩写

  + 总结：

    + 以上的目录开发规范有两种使用途径
      + 1.纯手工打造
      + 2.快速构建工具做  ---》  改造

+ ###2.前端命名规范：

  + ####BEM 和 OOCSS 针对的都是CSS命名规范

  + ####jslint 和 eslint   针对js使用规范

  + css规范

    + BEM规范
      + 1.概念：
        + Block Element Modifier，他是一种前端命名方法，旨在帮助开发者实现模块化，可复用，高可维护性和结构化的CSS代码
    + OOCSS规范
      + 1.概念
        + Object Oriented CSS, 面向对象的CSS，只在编写高可复用、低耦合和高扩展的CSS代码。
        + OOCSS是以面向对象的思想去定义样式，将抽象和实现分离，抽离公共代码
      + 总结
        + 将重用的东西当最一个对象来看，然后讲不同的属性放在另一个类名去
        + 举例：
          + 

+ ###3.前端工作规范

  + 日报、周报

    + 日报：

      + 今天上午你做了什么？
      + 下午做什么？
      + 遇到了什么问题？是否解决
      + 明天的计划（明天准备做什么）

    + 周报

      + 2016.07.25-2016.07.29周报：
            1.本周工作主要内容：
              A：完成了宏视云h5播放器升级及大数据上报；
              B：修复xk-h5播放器bug：在三星手机自带浏览器无法进行滑动seek; 
              C：admin-console后台管理系统初步完成终端访问页面和数据统计概览页面的制作；
            

        ```
        2.工作中存在的主要问题：
          A：webserver大数据展示页面移植到admin-console后台管理系统存在bootstrap与jquery.easyui冲突等几个兼容性问题；
          B：解决这个问题的思路可能不是最有效的方法，可能使用iframe会快些；使用iframe存在如何在easyui页面控制iframe页面及如何在浏览器窗口改变时，iframe也跟着改变等问题；
        
        3.下周工作计划：
          A：完成上周未完成的admin-console大数据展示页面的制作；
          B：完成工作以后，如果有时间的话尝试下用iframe解决；
          C：询问师兄有没有可以帮忙做的工作；
        ```

        邮件的发送

        1. 明确邮件发送谁？
           参与者： 一定要想清楚， 如果不清楚， 记得问一下你直接上司（同事）
        2. 邮件的主题： 
           - 主题必须有且仅有一个
           - 必要时， 可以添加： 【请批阅】 、 等字眼
        3. 邮件正文
           - 称呼要明确： 
           - 条理分明
             举例：
               各位老师好：
                   一下内容是xxx 请xxx
        4. 署名： 
           什么部分 什么职位  什么姓名 什么时间
        5. 附件
           需要说明附件是做什么的？
        6. 转发; 
           需要对原邮件进行说明。，然后写清楚自己的意图

+ ###4.开发文档的书写规范

  + ####1.html规范

    + 1.标签上属性的顺序建议如下： 

      class ( class 是为高可复用组件设计的,所以应处在第一位)
      id name (id 更加具体且应该尽量少使用,所以将它放在第二位)
      data-\*
      src for type href value
      placeholder title alt
      aria-\* role
      required readonly disabled

      + id/class 命名规则: BEM  OOCSS           SMACSS(扩展)

      + 注释规范(最好用英文)
        `
          <div class="container">
            <!-- 头部--start -->
            <header></header>
            <!-- 头部--end -->

        ```
        <!-- 内容--start -->
        <div class="content">
          
        </div>
        <!-- 内容--end -->
        
        <!-- 底部--start -->
        <footer>
        
        </footer>
        <!-- 底部--end -->
        ```

          </div>
        `

  + ####css规范

    + 1.属性顺序
      + 位置属性 ( position top right z-index display float etc.)
      + 大小 ( width height padding margin etc.)
      + 文字系列 ( font line-height letter-spacing color text-align ect.)
      + 背景 ( background border etc.)
      +  其他 ( animation transition etc.)
      + 以及注释的写法
    + 举例： 

      `

    ​      go--top{

    ​      position: fixed;
          right:20px;
          bottom: 50px;
          z-index: 1000;
          display:block;
          

    ```
      width: 50px;
      height: 200px;
    
      font-size: 16px;
    
      background: #ccc;
    
      opactiy: 0.5;
      transition: all 0.5s;
    
      <!-- 注释 -->
    }
    ```

      `

    1. 尽量不使用选择器 （css3选择器）

       .content.first-child
       举例：  
           <div class="content">
             <ul>
               <li>
                 <a href=""></a>
                 <a href=""></a>
                 <a href=""></a>
               </li>
             </ul>
             <ul>
               <li>
                 <a href=""></a>
                 <a href=""></a>
                 <a href=""></a>
               </li>
             </ul>
           </div>

    2. 属性使用缩写：
       举例： 
         `
           body{
             margin: 10px 0;
             background: url('./img.png') center;
           }
         `

    3. 去掉小数点前面的 0
       `
          body{
            margin: 10px .8px;
            background: url('./img.png') center;
          }

  + ####js规范

    1. #####语言规范

       - 声明变量必须加上 let 关键字.不要再使用 var
       - 优先使用箭头函数
       - 使用模板字符串取代连接字符串

    2. #####使用分号

       如果仅依靠语句间的隐式分隔,有时会很麻烦,使用分号更能清楚哪里是语句的起止,而且有些情况下,漏掉分号会出 BUG

    3. #####块内函数声明

       不要在块内声明一个函数,e.g.
           if (x) {
               function zxm() {}
           }

       如果确实需要,使用函数表达式来初始化变量
           if (x) {
               let foo = function() {}
           }

    4. #####循环注意

       forEach  map filter every some for..in  for...of   for循环  while   do...while

    5. #####命名规范： 

       **camel 表示驼峰名明发    pascal表示 首字母大写**
       变量名: 必须使用 camel 命名法
       参数名: 必须使用 camel 命名法
       函数名: 必须使用 camel 命名法
       方法/属性: 必须使用 camel 命名法
       私有 ( 保护 ) 成员: 必须以下划线开头
       常量名: 必须使用全部大写的下划线命名法,e.g. XTEP_HOST_API
       类名: 必须使用 pascal**(首字母大写)** 命名法
       枚举名: 必须使用 pascal**(首字母大写)**  命名法
       枚举的属性: 必须使用全部大写的下划线命名法,e.g. XTEP_HOST_API
       命名空间: 必须使用 camel**(驼峰命名)**  命名法
       语义: 命名同时还需要关注语义

    6. 声明：
       var  let  const  应该放在function 已进入函数的时候

       注释变量的功能及代表的含义,且应以字母顺序排序.每个变量单独占一行以便添加注释

       举例：
         var totalPrice = 1; //totalPrice表示商品购物车的总价   √
         var num = 10,totalNum = 100 ;           不建议

    7. 回调函数规范：
       回调函数统一使用 Promise 函数,回调成功的参数统一为 res,错误参数为 err

       `
           let callback = new Promise((resolve, reject) => {
               if (/* 异步操作成功 */){
                   resolve(value);
               } else {
                   reject(err);
               }
           });

       ```
       callback.then((res) => {
           console.log('成功回调！', res);
       }).catch((err) => {
           console.log('失败回调！', err);
       });
       ```

       `

    8. 标点规范
       js中统一使用反引号（``）或是单引号('')， 不使用双引号("")

    9. 函数默认值
       函数默认值写在其他参数后面
       `
           function zxm(a,b,name = 'zxm'){
               console.log(name)
           }

       `



## vue 快速构建项目

+ vue init webpack 文件名



## vue.js基础学习

+ vue介绍

  + 1.尤雨溪  google实习  阿里任职  weex研究团队（访问原生的库） vue.js是属于特德个人项目

  + 2.vue.js目前适用于中小型项目

  + 3.vue.js借鉴了 react 和 angular

  + 4.扩展

    + 和vue.js很类似一个库  avonlon。js
      + 也是一个个人项目
      + 司徒正美

  + 5.微博

    + 尤小右

  + 6.vue.js是一个前端的js的渐进式框架

    + *名词
      + 渐进式：越学越难（上手门槛低）

  + 7.vue.js什么时候正式发布

    + 2016年10月
    + github关注度：136K （不代表大陆地区）

  + 8.认识尤雨溪

  + ####9.前端的发展历程

    + js
    + jquery
    + MVC架构思维从后端引入到前端
      + backbone.js
      + angilar.js(15年)
      + react.js(15年)
      + vue.js(16年10月份 )
      + 研发12年以后，就是发布
    + 混合开发（流行技术）

  + 10.vue.js是一个MVVM框架

  + 11.vue.js数据也是单向的，我们称之为，单向数据流

  + 12.vue.js是不兼容**ie8**及其以下浏览器

  + ####13.只要是使用MVC框架数据，基本上都是单向数据流

+ ###MV* 模式

  + ####MVC框架介绍，

    + #####名称解释

      + **M：Model： 数据**
      + **V：View：视图**
      + **P：Presenter：提出者；推荐者；赠送者；任命者（中介，媒婆）**
      + **C：Controller： 控制器（业务逻辑）**
      + **VM：ViewModel：视图模型**

    + **库 VS 框架**

      + 库：工具
      + 框架：工具+生态圈

    + 常用在**饿了吗，淘宝**

    + **单项数据流**

    + **互动模式**接受用户指令时，MVC可以分成两种方式，一种是通过View接受指令，传递给Controller

      + ![1556616927051](C:\Users\shinelon\AppData\Local\Temp\1556616927051.png)

    + 另一种是直接通过controller接受指令

      + ![1556617017438](C:\Users\shinelon\AppData\Local\Temp\1556617017438.png)

  + MVC 后端引入  架构思维

  + 前端MVC   VS    后端MVC

    + 完全不同

  + MVC 衍生架构

    + backbone.js
      + ![1556626010768](C:\Users\shinelon\AppData\Local\Temp\1556626010768.png)
    + MVP
      + ![1556616801740](C:\Users\shinelon\AppData\Local\Temp\1556616801740.png)
    + MVVM
      + ![1556616774240](C:\Users\shinelon\AppData\Local\Temp\1556616774240.png)

+ ##Vue源代码

  + ###vue.js使用

    + 1.下载
      + cdn
        + 
      + 本地保存
        + vue.js文件
      + 模块化安装
        + npm i vue -D/-S
        + cnpm 
        + yarn

  + vue.js是MVVM框架

    + M ---》options中data
    + V ---》 options中el（模板）
    + VM ---》new Vue()  得到的实例，这个实例身上有很多的属性和方法

  + ### 初始化：

    + 1.必须有一个html容器，决定vue.js的作用范围

      + <div id="app"></div>

    + 2.初始化：

      + new Vue(options)
        + el  表示装载，将上面id为app的模板装载在 new Vue 的实例中，也确定了一个作用范围
        + data  
      + 注意：
        + 学习vue.js纪要学习配置项 && api

    + ```
      new Vue({
          el: '#app'  // 将new Vue实例装载在app这个div中，规定了new Vue出来的实例的作用范围
          el: `<div id="app">
                  {{msg}}
              </div>`,
          data: {
              // key: value
              msg: 'hello vue.js'
          }
      })
      
      <div id="app">
      	{{msg}}
      </div>
      ```

  + ### 数据绑定：

    + 名词：
      + mustauch语法糖：双大括号语法{{}}   支持js语法
    + el里面的数据绑定有三种写法：
      - {{ this.$data.msg }}
      - {{ this.msg }}
      - {{ msg }}
    + 注意事项：
      + 模板中的this值的是new Vue得到的实例，再模板中，this可以不写