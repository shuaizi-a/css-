>双飞翼布局：优化圣杯布局开启定位的问题
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>双飞翼布局</title>
    <style>
        * {
            margin: 0;
            padding: 0
        }
        
        #parent {
            height: 300px;
        }
        
        #left,
        #center,
        #right {
            height: 300px;
            /* 第一步：浮动; 三列在一行 */
            float: left;
        }
        
        #left,
        #right {
            width: 300px;
        }
        
        #left {
            background: #c9393a;
            /* 第三步 */
            margin-left: -100%;
        }
        
        #center {
            width: 100%;
            /* background-color: green; */
            /* 第二步：把center进行挤压，加到子元素的身上 */
        }
        
        #right {
            background-color: #cccccc;
            /* 第三步 */
            margin-left: -300px;
        }
        
        #inner {
            height: 300px;
            background-color: hotpink;
            /* 2.2 */
            margin-left: 310px;
            margin-right: 310px;
        }
    </style>
</head>

<body>
    <!-- 在圣杯的基础上 => 中间容器里面嵌套了一个子容器 => 解决圣杯定位再次移动的问题 -->
    <!-- 双飞翼没有在定位进行位置的移动 => 简化了圣杯的代码（简化定位） -->
    <div id="parent">
        <div id="center">
            <div id="inner"></div>
        </div>
        <div id="left"></div>
        <div id="right"></div>
    </div>
</body>

</html>
```