>后缀名是index.scssindex.scss

[sass插件](https://www.cnblogs.com/ldlx-mars/p/9242155.html)


#### sass变量
```scss
$width: 5em;

#main {
  width: $width;
}
```
#### 嵌套
```scss
#main {
  width: 97%;

  p, div {
    font-size: 2em;
    a { font-weight: bold; }
  }

  pre { font-size: 3em; }
}

// 父选择器 &
```
#### 混入 mixin
```scss
<!-- 代码片段 -->
@mixin large-text {
    font: {
        family: Arial;
        size: 20px;
        weight: bold;
    }
    color: #ff0000;
}

.page-title {
    @include large-text; // 引入代码片段
    padding: 4px;
    margin-top: 10px;
}
```
#### 扩展 extend
```scss
// 代码片段
.large-text {
    font: {
        family: Arial;
        size: 20px;
        weight: bold;
    }
    color: #ff0000;
}

.page-title {
    @extend .large-text; // 引入代码片段
    padding: 4px;
    margin-top: 10px;
}
```
#### 循环 loop
```scss
@for $i from 1 through 12 {
  .col-#{$i}{
    width: 100px;
  }
}
```
#### 模块化 import
```scss
@import "foo";
```