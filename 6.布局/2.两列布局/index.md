## 左边定宽，右列自适应
+ 利于float + margin实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #left {
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #cccccc;
      float: left;
      /* 重点 */
    }

    #right {
      height: 300px;
      background: #c9394a;
      margin-left: 400px;
    }
</style>
<body>
    <div id="left"></div>
    <div id="right"></div>
</body>
```
>如果子容器清除浮动，子元素会掉下来

+ 利于float + margin(fix)实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #left {
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #cccccc;
      float: left;
      /* 重点 */
      /* 提高层级 */
      position: relative;
      /* 重点 */
    }

    #right-fix {
      width: 100%;
      height: 300px;
      background: #00ffff;
      float: right;
      /* 重点 */
      margin-left: -400px;
      /* 重点 */
    }

    #right {
      margin-left: 400px;
      /* 重点 */
      height: 300px;
      background: #c9394a;
    }
</style>
<body>
    <div id="left"></div>
    <div id="right-fix">
        <div id="right"></div>
    </div>
</body>
```

+ 使用float + overflow实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #left {
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #cccccc;
      float: left;
      /* 重点 */
    }

    #right {
      height: 300px;
      background: #c9394a;
      /* BFC：形成一个隔离元素 条件之一 */
      overflow: hidden;
      /* 溢出隐藏 */
    }
</style>
<body>
    <div id="left"></div>
    <div id="right"></div>
</body>
```

+ 使用table + tabel-cell实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #parent {
      width: 100%;
      height: 300px;
      display: table;
    }

    #left {
      display: table-cell;
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #77f700;
    }

    #right {
      height: 300px;
      background: #c9394a;
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="right"></div>
    </div>
</body>
```

+ 使用posttion绝对定位实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #left {
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #cccccc;
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
    }

    #right {
      height: 300px;
      background: #c9394a;
      position: absolute;
      top: 0;
      left: 400px;
      right: 0;
      bottom: 0;
    }
</style>
<body>
    <div id="left"></div>
    <div id="right"></div>
</body>
```

+ 使用flex属性实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #parent {
      width: 100%;
      height: 300px;
      display: flex;
    }

    #left {
      width: 400px;
      /* 定宽 */
      height: 300px;
      background: #cccccc;
    }

    #right {
      flex: 1;
      height: 300px;
      background: #c9394a;
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="right"></div>
    </div>
</body>
```

+ 使用Grid实现实现
```html
<style>
    * {
      margin: 0;
      padding: 0
    }

    #parent {
      width: 100%;
      height: 300px;
      display: grid;
      /* 每个列的宽度左400 右自适应 */
      grid-template-columns: 400px auto;
    }

    #left {
      height: 300px;
      background: #cccccc;
    }

    #right {
      height: 300px;
      background: #c9394a;
    }
</style>
<body>
    <div id="parent">
        <div id="left"></div>
        <div id="right"></div>
    </div>
</body>
```