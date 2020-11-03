# 三列布局
## 两列定宽，一列自适应(右边)
## 左边定宽，右列自适应
+ 利于float + margin实现
```html
<style>
    *{margin:0; padding:0};

    #left{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #cccccc;
        float: left; /* 重点 */
    }

    #comter{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #fff;
        float: left; /* 重点 */
    }

    #right{
        width: 100%;
        height: 100%;
        background: #c9394a;
        margin-left: 400px;
    }
</style>
<body>
    <div id="left"></div>
    <div id="conter"></div>
    <div id="right"></div>
</body>
```

+ 使用float + overflow实现
```html
<style>
    *{margin:0; padding:0};

    #left{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #cccccc;
        float: left; /* 重点 */
    }

    #comter{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #fff;
        float: left; /* 重点 */
    }

    #right{
        width: 100%;
        height: 100%;
        background: #c9394a;
        
        /* BFC：形成一个隔离元素 条件之一 */
        overflow: hidden; /* 溢出隐藏 */
    }
</style>
<body>
    <div id="left"></div>
    <div id="conter"></div>
    <div id="right"></div>
</body>
```

+ 使用table + tabel-cell实现
```html
<style>
    *{margin:0; padding:0};
    
    #parent{
        width: 100%;
        display: table;
    }

    #left{
        display: table-cell;
        width: 400px; /* 定宽 */
        height: 100%;
        background: #cccccc;
        float: left; /* 重点 */
    }

    #comter{
        display: table-cell;
        width: 400px; /* 定宽 */
        height: 100%;
        background: #fff;
        float: left; /* 重点 */
    }

    #right{
        display: table-cell;
        width: 100%;
        height: 100%;
        background: #c9394a;
        
        /* BFC：形成一个隔离元素 条件之一 */
        overflow: hidden; /* 溢出隐藏 */
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="conter"></div>
        <div id="right"></div>
    </div>

</body>
```

+ 使用flex属性实现
```html
<style>
    *{margin:0; padding:0};

    #parent{
        width: 100%;
        height: 100%
        display: flex;
    }

    #left{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #cccccc;
    }

    #comter{
        width: 400px; /* 定宽 */
        height: 100%;
        background: #fff;
        float: left; /* 重点 */
    }

    #right{
        flex: 1;
        height: 100%;
        background: #c9394a;
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="conter"></div>
        <div id="right"></div>
    </div>
</body>
```

+ 使用Grid实现实现
```html
<style>
    *{margin:0; padding:0};

    #parent{
        width: 100%;
        height: 100%
        display: grid;
        /* 每个列的宽度左400 右自适应 */
        grid-template-columns: 400px 400px auto;
    }

    #left{
        height: 100%;
        background: #cccccc;
    }
    
    #comter{
        height: 100%;
        background: #fff;
        float: left; /* 重点 */
    }

    #right{
        height: 100%;
        background: #c9394a;
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="conter"></div>
        <div id="right"></div>
    </div>
</body>
```