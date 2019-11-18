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
    React元素
</div>

## 1. 元素是构成React应用的最小砖块

## 2. 元素描述了你在屏幕上想看到的内容。

```jsx
    const element = <h1>Hello, world</h1>;
```
与浏览器的 DOM 元素不同，React 元素是创建开销极小的普通对象。React DOM 会负责更新 DOM 来与 React 元素保持一致

## 3. 组件是由元素构成的