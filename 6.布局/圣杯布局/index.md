>圣杯布局：左右定宽，中间自适应 (center在left和right前面)
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>圣杯布局</title>
    <style>
        * {
            margin: 0;
            padding: 0
        }
        
        #parent {
            /* width: 100%; */
            height: 100px;
            padding: 0 310px;
        }
        
        #center {
            width: 100%;
            /* 定宽 */
            height: 100%;
            background: red;
            float: left;
            /* 重点 */
        }
        
        #left {
            width: 300px;
            /* 定宽 */
            height: 100%;
            background: #cccccc;
            float: left;
            /* 重点 */
            margin-left: -100%;
            position: relative;
            left: -310px;
        }
        
        #right {
            width: 300px;
            /* 定宽 */
            height: 100%;
            background: #2638a1;
            /* 重点 */
            float: left;
            margin-left: -300px;
            position: relative;
            right: -310px;
        }
    </style>
</head>

<body>
    <div id="parent">
        <div id="center"></div>
        <div id="left"></div>
        <div id="right"></div>
    </div>
</body>

</html>
```