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
    UMI
</div>

#### 1.介绍
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "#FF7F50" style = "font-weight: bold;">  
        1. umi，中文可发音为乌米，是一个可插拔的企业级 react 应用框架
    </font>
    <br>
    <font color = "#FF7F50" style = "font-weight: bold;">
        2. umi 是蚂蚁金服的底层前端框架，已直接或间接地服务了 600+ 应用
    </font>
</div>



#### 2.特性

- 📦 开箱即用，内置 react、react-router 等
- 🏈 类 next.js 且功能完备的路由约定，同时支持配置的路由方式
- 🎉 完善的插件体系，覆盖从源码到构建产物的每个生命周期
- 🚀 高性能，通过插件支持 PWA、以路由为单元的 code splitting 等
- 💈 支持静态页面导出，适配各种环境，比如中台业务、无线业务、egg、支付宝钱包、云凤蝶等
- 🚄 开发启动快，支持一键开启 dll 等
- 🐠 一键兼容到 IE9，基于 umi-plugin-polyfills
- 🍁 完善的 TypeScript 支持，包括 d.ts 定义和 umi test
- 🌴 与 dva 数据流的深入融合，支持 duck directory、model 的自动加载、code splitting 等等

#### 3.开发团队
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;margin-top: 15px;"
>
    <font color = "#FF7F50" style = "font-weight: bold;">  
        蚂蚁金服开发团队
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
    Umi快速上手
</div>

<div
    style = "background: #000;text-align: justify;padding: 10px 8px;letter-spacing: 2px;color: green;font-weight: bold;"
>
    $ npm install umi -g<br>
    $ mkdir app<br>
    $ cd app <br>
    $ umi g page index<br>
    $ umi g page user<br>
    $ umi dev 
</div>



#### 4. DVA项目内容介绍

##### 目录介绍

<div
    style = "background: #ccc;text-align: justify;padding: 10px 0px;letter-spacing: 2px;color: green;font-weight: bold;"
>

└── .umi						<font color = "#FF7F50"> 项目运行临时文件 </font><br>
└── pages						<font color = "#FF7F50"> 路由对应组件目录 </font><br>
└──── index.js <font color = "#FF7F50"> 首页组件 </font><br>
└──── index.css <font color = "#FF7F50">首页组件样式 </font><br>
└──── user.js <font color = "#FF7F50"> user 组件 </font><br>
└──── user.css <font color = "#FF7F50">user组件样式 </font><br>

</div>



