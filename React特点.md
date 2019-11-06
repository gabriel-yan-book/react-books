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
    React特点
</div>

##### 1. Virtual DOM
##### 2. Diff算法 
> React 16版本之后发布了一个新的算法： React Filber 算法

<font color = "red" style = "text-decoration: underline;font-weight: bold;font-size: 24px;"> React Filber </font>

<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;text-indent: 2em;"
>
当React决定要加载或者更新组件树时，会做很多事，比如调用各个组件的生命周期函数，计算和比对Virtual DOM，最后更新DOM树，这整个过程是同步进行的，也就是说只要一个加载或者更新过程开始，中途不会中断。因为JavaScript单线程的特点，如果组件树很大的时候，每个同步任务耗时太长，就会出现卡顿。

<p>
<font color = "red">React Fiber的方法其实很简单——分片。把一个耗时长的任务分成很多小片</font>，每一个小片的运行时间很短，虽然总时间依然很长，但是在每个小片执行完之后，都给其他任务一个执行的机会，这样唯一的线程就不会被独占，其他任务依然有运行的机会。
</p>

</div>

##### 3. 组件系统【 Component 】
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;text-indent: 2em;"
>
react最核心的思想是将页面中任何一个区域或者元素都可以看做一个组件
</div>

##### 4. 单向数据流 
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;text-indent: 2em;"
>
reactjs的核心内容就是数据绑定，所谓数据绑定指的是只要将一些服务端的数据和前端页面绑定好，开发者只关注实现业务就行了
</div>

##### 5. JSX语法
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;text-indent: 2em;"
>
    为了更加便利的模拟DOM结构，我们使用了JSX语法，可以让我们在JS中编译DOM结构
    <p> React可以通过脚手架【 webpack构建 】来对JSX进行编译 </p>
</div>

##### 6. 函数式编程
<div
    style = "background: #ccc;text-align: justify;padding: 10px 8px;letter-spacing: 2px;text-indent: 2em;"
>
    JS的最大特点就是函数式编程，在React中，函数式编程可谓式无处不见
</div>