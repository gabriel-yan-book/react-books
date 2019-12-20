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
    React 状态管理 - Flux
</div>

## 1. Flux介绍
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">
    在2013年，Facebook让React亮相的同时推出了Flux框架，React的初衷实际上是用来替代jQuery的，Flux实际上就可以用来替代Backbone.js，Ember.js等一系列MVC架构的前端JS框架
    </font>
</div>
<br>
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">
    React只是一个MVC中的V(视图层)，只管页面中的渲染，一旦有数据管理的时候，React本身的能力就不足以支撑复杂组件结构的项目，在传统的MVC中，就需要用到Model和Controller。Facebook对于当时世面上的MVC框架并不满意，于是就有了Flux, 但Flux并不是一个MVC框架，他是一种新的思想（ 新的架构思想 ）
    </font>
</div>

## 2. Flux图示
![](https://ftp.bmp.ovh/imgs/2019/12/40decbcc5f726bce.png)
## 3. Flux图示解析
1. Flux组件部分
   - View： 视图层  （ 用React的组件来代替 ）
   - ActionCreators（动作创造者）：视图层发出的消息（比如mouseClick）
   - Dispatcher（派发器）：用来接收Actions、执行回调函数
   - Store（数据层）：用来存放应用的状态，一旦发生变动，就提醒Views要更新页面
2. 后端数据交互
   - 交由 ActionCreators 来进行处理

## 4. Flux使用流程以及案例代码

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    Flux工作流程
</font>

1. 组件获取到store中保存的数据挂载在自己的状态上
2. 用户产生了操作，调用actions的方法
3. actions接收到了用户的操作，进行一系列的逻辑代码、异步操作
4. 然后actions会创建出对应的action，action带有标识性的属性
5. actions调用dispatcher的dispatch方法将action传递给dispatcher
6. dispatcher接收到action并根据标识信息判断之后，调用store的更改数据的方法
7. store的方法被调用后，更改状态，并触发自己的某一个事件
8. store更改状态后事件被触发，该事件的处理程序会通知view去获取最新的数据


<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    Flux案例代码
</font>

1. 要想使用FLux架构思维，需要通过一个工具进行使用， 这个工具就是flux
2. 安装 flux 
$ yarn  add flux
3. 在src目录下 新建store目录，里面新建index.js
   - store有两个功能
     - 存储数据
     - 当数据发生改变时，视图要进行更新 （ 当前组件中的state发生了改变，从新从store中获取数据，要想重新复制，那么要通过事件的发布，订阅 ） 
```js
        // store/index.js
    
          const EventEmitter = require( 'events' ).EventEmitter
    
          const store = {
            ...EventEmitter.prototype,
            state: {
              count: 0
            },
            getState () {
              return this.state
            }
          }
          export default store 
```
4. 将store中的数据显示在组件（视图）中
```js
         import store from './store'
       
         class xxx extends React.Component{
           constructor () {
             super()
             this.state = {
               count: store.getState().count
             }
           }
       
           render () {
             return (
               <div>
                 <p> { this.state.count } </p>
               </div>
             )
           }
         }
```
5. 用户操作，用户点击按钮，执行当前组件中的方法，这个方法的逻辑实际上是actionCreators中的方法
6. 创建actionCreators.js
   - actions的发送要通过dispatcher来发送

    ``` js
            import * as type from './type'
            import dispatcher from './dispatcher';
            const actionCreators = {
              increment () {
                // 创建动作
                let actions = {
                  type: type.INCRMENT
                }
                // dispatcher来通过dispatch  发送actions
                dispatcher.dispatch( actions )
              }
            }
       
            export default actionCreators
    ```
7. 创建dispatcher.js
```js
         import { Dispatcher } from 'flux';
         import * as type from './type'
         import state from './state'
         const dispatcher = new Dispatcher()
       
         // dispatcher.register( callback )
       
         dispatcher.register( ( actions) => {
           switch ( actions.type ) {
             case type.INCRMENT:
                 // 用户操作了
                 state.count++
               break;
           
             default:
               break;
           }
         })
       
         export default dispatcher
```
8. 通过store的事件的发布和订阅进行 当前组件中 state 的重新赋值
   - 当我们点击按钮是，要通过store的事件的订阅给当前组件的state重新赋值，要想这样做，我们必须进行事件的发布
   - 难点： 这个事件的发布往哪里写？ 
   - 组件的生命周期中，数据可以进行一次修改的可以往 componentWillMount // componentDidMount
   - 难点： 这个事件的订阅那里写？
   - 当我们点击按钮的时候，就要修改当前组件的state,也就是要进行事件的订阅
```js
         import React from 'react';
         import logo from './logo.svg';
         import './App.css';
       
         import store from './store'
         import actionCreators from './store/actionCreators';
       
         class App extends React.Component {
           
           constructor () {
             super()
             this.state = {
               count: store.getState().count
             }
           }
       
           increment () {
             actionCreators.increment()
             store.emit('count')
           }
       
           componentDidMount () {
             store.on('count', () => {
               this.setState({
                 count: store.getState().count
               })
             })
           }
       
           render () {
             return (
               <div>
                 <h3> flux </h3>
                 <button onClick = { this.increment }> + </button>
                 <p> count: { this.state.count } </p>
               </div>
             )
           }
         }
       
         export default App;
```


