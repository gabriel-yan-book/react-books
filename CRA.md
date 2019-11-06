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
    "
> 
    CRA 
</div>

#### 1.CRA介绍

<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    全称：
    <font color = "#FF7F50" style = "font-weight: bold;">  
        create-react-app
    </font>
    <br>
    React应用程序快速创建脚手架：
     <font color = "#FF7F50" style = "font-weight: bold;">  
        底层： webpack
    </font>
    <br>
    创作团队：
     <font color = "#FF7F50" style = "font-weight: bold;">  
        Facebook
    </font>
</div>


#### 2. CRA应用
<font style = "color: #FF7F50;font-weight: bold;">全局安装</font>
<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    $ npm i create-react-app -g<br>
    $ create-react-app app<br>
    $ cd app <br>
    $ yarn start<br>
</div>
or
<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    $ cnpm i create-react-app -g  <br>
    $ create-react-app app<br>
    $ cd app <br>
    $ yarn start <br>
</div>


<font style = "color: #FF7F50;font-weight: bold;">npx创建CRA项目</font>
![](https://camo.githubusercontent.com/e4f2feecb8bc0d58c1f2e31f97b2856a04b50ef3/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f66616365626f6f6b2f6372656174652d72656163742d61707040323762343261633765666130313866323534313135336162333064363331383066356661333965302f73637265656e636173742e737667)

#### 3. CRA 命令介绍
<div
    style = "margin-bottom: 15px;background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    yarn start  -- 表示开发环境下运行整个项目
</div>
<div
    style = "margin-bottom: 15px;background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    yarn build  -- 表示生产环境打包，进行编译、压缩等操作
</div>
<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    yarn eject  -- 配置文件抽离，将项目的webpack配置和项目运行文件从node_modules的react-script中抽离到项目根目录
</div>


#### 4. CRA项目内容介绍

1. 目录介绍
<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
├── README.md							<font color = "#FF7F50">使用方法的文档</font> <br>
├── node_modules					<font color = "#FF7F50">所有的依赖安装的目录</font> <br>
├── yarn-lock.json			<font color = "#FF7F50">锁定安装时的包的版本号,保证团队的依赖能保证一致。</font> <br>
├── package.json					 <font color = "#FF7F50">项目依赖配置记录文件 、 记录项目脚本命令 </font><br>
├── public								   <font color = "#FF7F50">静态公共目录（ 生产环境 ） 不会被webpack编译 </font><br>
├── config                   <font color = "#FF7F50">项目webpack配置文件 </font><br>
├── scripts                  <font color = "#FF7F50">项目wepback脚本命令执行文件 </font><br>
└── src									<font color = "#FF7F50">开发用的源代码目录 </font><br>
└──── index.js <font color = "#FF7F50">项目入口文件 </font><br>
└──── index.css <font color = "#FF7F50">项目全局样式 </font><br>
└──── App.js <font color = "#FF7F50">构建了一个App组件，是项目最大的组件 【 类似根组件 】</font><br>
└──── App.css <font color = "#FF7F50">是App组件的样式文件 </font><br>
└──── App.test.js <font color = "#FF7F50">是App组件测试文件  </font><br>
└──── logo.svg <font color = "#FF7F50">初始项目的界面logo </font><br>
└──── serverWorker <font color = "#FF7F50">内部文件，我们不操作 </font><br>
</div>

2. 项目解读
    1. 先查看 package.json 文件，通过npm脚本来确定项目启动命令
    2. 在查看项目入口文件 src/index.js
    3. 查看项目最大的组件App.js
