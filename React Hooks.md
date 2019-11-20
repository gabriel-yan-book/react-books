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
    React Hooks
</div>

### 1. React Hooks 是什么？

<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
       Hook 是 React 16.8 的新增特性。它可以让你在不编写 class 的情况下使用 state 以及其他的 React 特性
    </font>
</div>

### 2. React Hooks特点
1. 完全可选：  你无需重写任何已有代码就可以在一些组件中尝试 Hook。但是如果你不想，你不必现在就去学习或使用 Hook。
2. 100% 向后兼容的。 Hook 不包含任何破坏性改动。
3. 现在可用。 Hook 已发布于 v16.8.0。
4. 没有计划从 React 中移除 class
5. Hook 不会影响你对 React 概念的理解

### 3. React Hooks作用 【 为什么要使用Hooks 】
1. 解决在组件之间复用状态逻辑很难
2. 解决复杂组件变得难以理解
3. 解决难以理解的 class


### 4. React Hooks 有哪些？
1. 基础 Hook
    - useState  
      - 返回一个 state，以及更新 state 的函数。 
    - useEffect 
      - 该 Hook 接收一个包含命令式、且可能有副作用代码的函数
    - useContext 
      - 接收一个 context 对象（React.createContext 的返回值）并返回该 context 的当前值
2. 额外的 Hook
    - useReducer 
      - useState 的替代方案。它接收一个形如 (state, action) => newState 的 reducer，并返回当前的 state 以及与其配套的 dispatch 方法
    - useCallback 
      - 返回一个 memoized 回调函数
    - useMemo 
      - 返回一个 memoized 值
    - useRef   
      - useRef 返回一个可变的 ref 对象
    - useImperativeHandle 
      - useImperativeHandle 可以让你在使用 ref 时自定义暴露给父组件的实例值
    - useLayoutEffect 
      - 其函数签名与 useEffect 相同，但它会在所有的 DOM 变更之后同步调用 effect。可以使用它来读取 DOM 布局并同步触发重渲染。在浏览器执行绘制之前，useLayoutEffect 内部的更新计划将被同步刷新。
    - useDebugValue   
      - useDebugValue 可用于在 React 开发者工具中显示自定义 hook 的标签。


### 5. 简单使用一下几个常用React Hooks

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    useState - 代码演示
</font>

```js
    function Counter({initialCount}) {
        const [count, setCount] = useState(initialCount);
        /* 
            * count 是定义的state 
            * setCount 是用于更新count的方法
        */
        return (
            <div>
                Count: {count}
                <button onClick={() => setCount(initialCount)}>Reset</button>
                <button onClick={() => setCount(prevCount => prevCount - 1)}>-</button>
                <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
            </div>
        );
    }
```

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    useEffect - 代码演示
</font>

> 在函数组件主体内（这里指在 React 渲染阶段）改变 DOM、添加订阅、设置定时器、记录日志以及执行其他包含副作用的操作都是不被允许的，因为这可能会产生莫名其妙的 bug 并破坏 UI 的一致性。 useEffect提供了这些副作用操作的可能

```js
    function Counter({initialCount}) {
        const [count, setCount] = useState(initialCount);
        /* 
            * count 是定义的state 
            * setCount 是用于更新count的方法
        */
        return (
            <div>
                Count: {count}
                <button onClick={() => setCount(initialCount)}>Reset</button>
                <button onClick={() => setCount(prevCount => prevCount - 1)}>-</button>
                <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
            </div>
        );
    }
```

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    useContext - 代码演示
</font>

> - useContext(MyContext) 相当于 class 组件中的 static contextType = MyContext
> - useContext(MyContext) 只是让你能够读取 context 的值以及订阅 context 的变化。你仍然需要在上层组件树中使用 <MyContext.Provider> 来为下层组件提供 context

```js
   import React from 'react'
   const themes = {
        light: {
            foreground: "#000000",
            background: "#eeeeee"
        },
        dark: {
            foreground: "#ffffff",
            background: "#222222"
        }
    };

    const ThemeContext = React.createContext(themes.light);

    function App() {
        return (
            <ThemeContext.Provider value={themes.dark}>
            <Toolbar />
            </ThemeContext.Provider>
        );
    }

    function Toolbar(props) {
        return (
            <div>
                <ThemedButton />
            </div>
        );
    }

    function ThemedButton() {
        const theme = useContext(ThemeContext);
        const style = { background: theme.background, color: theme.foreground }
        return (
            <button style={ style }>
                I am styled by theme context!
            </button>
        );
    }
```