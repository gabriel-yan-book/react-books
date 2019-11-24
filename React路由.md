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
    React 路由
</div>

## 1. 为什么要使用路由？

1. 单页面实现页面的切换【 SPA的实现 】

2. 可以通过URL对页面进行定位

3. 语义化组织资源

## 2. react-router版本
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        react-router 目前在第五个版本
    </font>
</div>

## 3. react-router官网文档
  https://reacttraining.com/react-router/web/guides/quick-start

## 4. react-router效果演示
<!-- <font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    移动端项目案例
</font>
<br/>
<img src = "http://test.fe.ptdev.cn/elm/screenshots/confrimOrder.gif"/>

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    pc端项目案例
</font>
<img src = "http://static.oschina.net/uploads/space/2017/1018/074540_IE6W_2720166.gif"/> -->

<hr/>

## 5. react-router使用

1. 创建React项目
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
       $ npx create-react-app router_app
       <br/>
       $ cd router_app 
       <br/>
       $ yarn start
    </font>
</div>

2. 安装react-router-dom
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
       $ yarn add react-router-dom
    </font>
</div>

3. 在项目入口文件中配置路由模式
```js
    import React from 'react';
    import ReactDOM from 'react-dom';
    import './index.css';
    import App from './App';
    import * as serviceWorker from './serviceWorker';

    /* 
        * 1. React路由模式有两种： 
            1. HashRouter[ #/home 传统浏览器模式 hashchange ]  
            2. BrowserRouter[ /home  h5 history模式 ]
        * 2. BrowserRouter需要后端支持
        * 3. as的作用是给一个模块起一个别名
    */
    import { BrowserRouter as Router } from 'react-router-dom'

    ReactDOM.render(
    <Router>
        <App />
    </Router>
    , document.getElementById('root'));

    serviceWorker.unregister();
```

4. 在项目中新建index.js,     src/router/index.js
```js
    import React, { Component,Fragment } from 'react'
    import Home from './../pages/home/index';
    import Recommend from './../pages/recommend/index';
    import Category from './../pages/category/index';
    import Mine from './../pages/mine/index';
    import ShopCar from './../pages/shopcar/index';
    import NotFound from './../pages/notfound/index';
    import Login from './../pages/login/index';
    import Register from './../pages/register/index';
    import List from './../pages/list/index';
    import Detail from './../pages/detail/index';
    import { Route,Switch,Redirect,withRouter } from 'react-router-dom'
    /* 
        * Route是用来通过path路径来匹配对应的组件,一个Route组件就是一个路由的配置
            * path    路由路径
            * component  路由对应的组件
            * render 可以渲染一个组件
            * children 子组件
            ! component  / render /children 选一个使用

            * component vs render vs children 
            1. 使用了Route并使用了component属性之后，我们的组件称之为路由组件，有路由属性【 history/location/match 】
            2. 使用render的话，我们发现组件的路由属性是没有的，但是我们可以给我们的组件绑定数据了
            3. 使用children的话，我们不仅可以绑定数据，也可以有路由属性 
        * Switch表示一次只渲染一个路由
        * Redirect  重定向组件
        
        ! exact  它表示路径完全匹配      /        /home       /home/hot
    */

    export default class RouteComp extends Component{
        render () {
            return (
                <div>
                    <Switch>
                        <Redirect from = "/" to = "/home" exact/>
                        <Route path = "/home" component = { Home }/>
                        <Route path = "/recommend" component = { Recommend }/>
                        <Route path = "/category" component = { Category }/>
                        <Route path = "/shopcar" component = { ShopCar }/>
                        {/* <Route path = "/mine" component = { Mine }/> */}
                        {/* <Route path = "/mine" render = {() => <Mine name = { name } />}/> */}
                        <Route path = "/mine" children = {() => <Mine name = { name } />}/>
                        <Route path = "/login" component = { Login } />
                        <Route path = "/register" component = { Register } />
                        <Route path = "/list/:id" component = { List } />
                        <Route path = "/detail/:id" component = { Detail } />
                        <Route  component = { NotFound }/> 
                    </Switch>
                </div>
            )
        }
    }
```

5. 二级路由配置
```js
    import React,{ Component } from 'react'
    import { Route,NavLink } from 'react-router-dom'
    import Hot from './Hot.js'
    import Coming from './Coming.js'
    class Home extends Component{
        render () {
            return (
                <div>
                    {/* 二级路由导航 */}
                    <NavLink to = "/home/hot"> 正在热映 </NavLink>
                    <NavLink to = "/home/coming"> 即将上映 </NavLink>
                    {/* 二级路由展示区域 */}
                    <Route path = "/home/hot" Component = { Hot } />
                    <Route path = "/home/coming" Component = { Coming } />
                </div>
            )
        }
    }
```

6. 动态路由
> - 路由传参
> - 路由接参
> - 案例效果
>   - 移动端分类 -> 列表 -> 详情 -> 购物车

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    路由传参 - 代码演示
</font>

```js
    import React, { Component,Fragment } from 'react'
    import { Link } from 'react-router-dom'
    class Category extends Component{
        render () {
            const route = {
                pathname: '/list/1',
                search: 'cid=23&shopname=电脑'
            }
            return (
                <Fragment>
                    <Link
                        to = { route }
                    >
                        商品一
                    </Link>
                </Fragment>
            )
        }
    }

```
<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    路由接参 - 代码演示
</font>

```js
    import React, { Component,Fragment } from 'react'
    import { Link } from 'react-router-dom'
    import qs from 'querystring'
    class Category extends Component{
        render () {
            const search = qs.parse( this.props.location.search.slice(1) )
            const params = this.props.location.params
            return (
                <Fragment>
                    <p> 接收的id为： { params.id } </p>
                    <p> 接收的cid为： { search.cid } </p>
                    <p> 接收的shopname为： { search.shopname } </p>
                </Fragment>
            )
        }
    }

```

7. 路由监听
> - 移动端
>   - 某些界面效果显示有无

