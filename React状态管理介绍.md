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
    React 状态管理  
</div>

##  1. React状态管理出现的原因

<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        facebook 开发团队对MVC架构并不是很满意 ,所以导致React没有采用MVC架构思想，React单纯只能看做是MVC中V,作为一个完整的软件架构，那么需要包含另外两个部分，所以React需要补全这两个部分

    </font>
</div>

## 2. React状态管理的发展
<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    Flux出现
</font>
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;"> 在React发布的同时，facebook团队发布了一个软件架构思维： Flux  
    </font>
    <font color = "greenyellow" style = "font-weight: bold;">  
       在Flux软件架构思维中，React只是其中一部分，充当V 
    </font>
</div>
<br>

<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    Redux出现
</font>
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        后期Flux发展改进，诞生了一个新的架构： Redux 
    </font>
</div>
<br>
<font color = "red" style = "font-size: 18px;font-weight: bold;background: black;padding: 8px 10px;">
    Mobx出现
</font>
<div
    style = "background: black;text-align: justify;padding: 10px 8px;letter-spacing: 2px;"
>
    <font color = "greenyellow" style = "font-weight: bold;">  
        Redux也存在不便利性，为了弥补Redux的缺陷，开发了mobx
    </font>
</div>

