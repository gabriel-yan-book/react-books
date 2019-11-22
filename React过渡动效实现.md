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
  React过渡动效
</div>

## 1. 说明
- 过渡动效在项目中是一个必须的业务
- React过渡动效通过react-transition-group这个第三方模块来实现

## 2. 代码演示

```js
  import React, { Component } from 'react'
  import { CSSTransition } from 'react-transition-group'

  export default class Home extends Component {
    
    constructor(props) {
      super(props)
    
      this.state = {
        flag: true 
      }
    }
    
    changeFlag = () => {
      this.setState({
        flag: !this.state.flag 
      })
    }

    render() {
      const { flag } = this.state 
      const classname = {
              enter: 'animated', // 刚刚进入那一刻
              enterActive: 'slideInLeft',// 进入的整个过程
              exit: 'animated',//离开的那一刻
              exitActive: 'slideOutLeft'// 离开的过程
            }
      return (
        <div>
          <button onClick = { this.changeFlag }> 点击 </button>
          {/* p就是我想要给p添加动作效果 */}
          <CSSTransition
            in = { flag } //in的值必须变化的
            timeout = { 1000 } // 动画的延迟时间
            unmountOnExit
            classNames = { classname }
          >
            {/* 使用CSSTransition组件包裹动画元素 */}
            <p> 动画元素 </p>
          </CSSTransition>
        </div>
      )
    }
  }


```