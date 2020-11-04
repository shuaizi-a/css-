>等分布局：把一行分成若干列，没一列的宽度值是相同的值
## float实现
```html
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        .col1,
        .col2,
        .col3,
        .col4 {
            height: 300px;
            /* 等分 */
            width: 25%;
            /* 百分比需要自己计算，使用浮动会导致父元素高度塌陷 */
            float: left;
        }
        /* 
            解决因为浮动导致父元素塌陷的方法
            1：固定高度 （不推荐，除非高度是固定的）
            2：overflow：hidden；=》 BFC 特点：把浮动的高度计算进去
            3：clear：both；清除浮动 加到浮动元素末尾子元素上
            4：伪类利于伪元素 :::after
                .clearfix:::after{
                    content:'';
                    display: block;
                    clear:both;
                }
         */
        
        .col1 {
            background: #ac0c0c;
        }
        
        .col2 {
            background: #c29313;
        }
        
        .col3 {
            background: #1fe405;
        }
        
        .col4 {
            background: #09a1dd;
        }
    </style>
</head>

<body>
    <div id="parent">
        <div class="col1"></div>
        <div class="col2"></div>
        <div class="col3"></div>
        <div class="col4"></div>
    </div>
</body>
```
## table实现
```html
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        #parent {
            width: 100%;
            display: table;
        }
        
        .col1,
        .col2,
        .col3,
        .col4 {
            height: 300px;
            /* 等分 */
            display: table-cell;
        }
        
        .col1 {
            background: #ac0c0c;
        }
        
        .col2 {
            background: #c29313;
        }
        
        .col3 {
            background: #1fe405;
        }
        
        .col4 {
            background: #09a1dd;
        }
    </style>
</head>

<body>
    <div id="parent">
        <div class="col1"></div>
        <div class="col2"></div>
        <div class="col3"></div>
        <div class="col4"></div>
    </div>
</body>

```
## flex实现
```html
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        
        #parent {
            width: 100%;
            display: flex;
        }
        
        .col1,
        .col2,
        .col3,
        .col4 {
            height: 300px;
            /* 等分 */
            flex: 1;
        }
        
        .col1 {
            background: #ac0c0c;
        }
        
        .col2 {
            background: #c29313;
        }
        
        .col3 {
            background: #1fe405;
        }
        
        .col4 {
            background: #09a1dd;
        }
    </style>
</head>

<body>
    <div id="parent">
        <div class="col1"></div>
        <div class="col2"></div>
        <div class="col3"></div>
        <div class="col4"></div>
    </div>
</body>
```
