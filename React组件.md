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
    React组件
</div>

## 1. 什么是组件？
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        组件是由元素构成的一个聚合体
    </font>
</div>

### 2. React - 函数组件
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        定义组件最简单的方式就是编写 JavaScript 函数：
    </font>
</div>
```js
    /* 声明函数组件 */
    function Welcome(props) {
        return <h1>Hello, {props.name}</h1>;
    }
    //OR
    const Hello = props => <h1> Hello React函数组件 </h1>
```
### 3. React - 类组件
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        我们还可以使用 ES6 的 class 来定义组件
    </font>
</div>
```js
    /* 声明类组件 */
    import React,{ Component } from 'react'
    class Welcome extends Component{
        render () { // 通过render函数来渲染一个jsx结构
            return (
                <div>
                    欢迎使用西阁的React笔记
                <div>
            )
        }
    }
```

