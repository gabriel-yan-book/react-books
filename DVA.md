<div
    style = "
        width: 100%;
        height: 50px;
        background: #00FFFF;
        color: black;
        line-height: 50px;
        padding-left: 15px;
        font-size: 24px;
        font-weight: bold;
    "
> 
    DVA介绍
</div>

#### 1.名称由来
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "#FF7F50" style = "font-weight: bold;">  
        D.Va拥有一部强大的机甲，它具有两台全自动的近距离聚变机炮、可以使机甲飞跃敌人或障碍物的推进器、 还有可以抵御来自正面的远程攻击的防御矩阵
    </font>
</div>

<p style = "margin: 20px 8px;padding-left: 25px;">___来自守望先锋 </p>
<div style = "width: 250px;height: 200px;margin-left: 25px;border-radius: 10px;overflow: hidden;">
<img style = "width: 100%;height: 100%;" src = "https://zos.alipayobjects.com/rmsportal/psagSCVHOKQVqqNjjMdf.jpg"/>
</div>


#### 2.DVA是什么？
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;margin-top: 15px;"
>
    <font color = "#FF7F50" style = "font-weight: bold;">  
        DVA是一个轻量级的应用框架
    </font>
</div>

#### 3.开发团队
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;margin-top: 15px;"
>
    <font color = "#FF7F50" style = "font-weight: bold;">  
        支付宝开发团队
    </font>
</div>



<div
    style = "
        width: 100%;
        height: 50px;
        background: #00FFFF;
        color: black;
        line-height: 50px;
        padding-left: 15px;
        font-size: 24px;
        font-weight: bold;
        margin-bottom: 40px;
        margin-top: 20px;
    "
> 
    DVA应用创建
</div>

<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    $ npm install dva-cli -g<br>
    $ dva new app<br>
    $ cd app <br>
    $ yarn start<br>
</div>



#### 4. DVA项目内容介绍

1. 目录介绍
<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
├── mock							<font color = "#FF7F50">mock模拟数据</font> <br>
├── node_modules					<font color = "#FF7F50">所有的依赖安装的目录</font> <br>
├── editorconfig					<font color = "#FF7F50">项目编辑器配置记录文件</font> <br>
├── eslintrc					<font color = "#FF7F50"> eslint代码检测配置文件 </font> <br>
├── .gitignore					<font color = "#FF7F50">  git上传忽略性配置文件  </font> <br>
├── .webpackrc					<font color = "#FF7F50">  webpack配置文件  </font> <br>
├── package.json					 <font color = "#FF7F50">项目依赖配置记录文件 、 记录项目脚本命令 </font><br>
├── public								   <font color = "#FF7F50">静态公共目录（ 生产环境 ） 不会被webpack编译 </font><br>
└── src									<font color = "#FF7F50">开发用的源代码目录 </font><br>
└──── index.js <font color = "#FF7F50">项目入口文件 </font><br>
└──── index.css <font color = "#FF7F50">项目全局样式 </font><br>
└──── router.js <font color = "#FF7F50"> 项目路由配置 </font><br>
└──── App.css <font color = "#FF7F50">是App组件的样式文件 </font><br>
└──── App.test.js <font color = "#FF7F50">是App组件测试文件  </font><br>
└──── logo.svg <font color = "#FF7F50">初始项目的界面logo </font><br>
└──── serverWorker <font color = "#FF7F50">内部文件，我们不操作 </font><br>
└──── assets <font color = "#FF7F50"> 开发环境下的静态资源文件夹，会被 wepback 编译 </font><br>
└──── components <font color = "#FF7F50"> 组件存放目录 </font><br>
└──── model <font color = "#FF7F50"> redux </font><br>
└──── services <font color = "#FF7F50"> 数据请求 </font><br>
└──────── example.js <font color = "#FF7F50"> exmaple组件中的数据请求 </font><br>
└──── routes <font color = "#FF7F50"> 路由对应的组件 </font><br>
└──────── index.js <font color = "#FF7F50"> 项目默认页面 </font><br>
└──── utils <font color = "#FF7F50"> 项目封装库 </font><br>
└─────── request.js <font color = "#FF7F50"> 封装fetch数据请求 </font><br>

</div>

2. 项目解读
    1. 先查看 package.json 文件，通过npm脚本来确定项目启动命令 - 通过roadhog来启动项目
    2. 在查看项目入口文件 src/index.js 
        - 确定了redux引入的形式
        - 确定了路由的引用
    3. 查看路由的配置  router.js
    4. 查看路由配置对应渲染的组件
    5. 查看状态共享的redux如何使用

