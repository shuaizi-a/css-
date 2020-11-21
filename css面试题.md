## 什么是BFC(块级格式化上下文)

>1、BFC全称：Block Formatting Context，译为块级格式化上下文，它是CSS2.1规范定义的，关于CSS渲染定位的一个概念

>2、能够解决因浮动造成的父元素塌陷问题

>3、能够解决div浮动造成的遮盖问题【overflow:hidden; 触发bfc来解决遮挡问题】

>4、解决margin塌陷问题【overflow:hidden; 产生bfc来解决】

## 什么是IFC(内联格式化上下文)
>1. IFC全称：Inline Formatting Contexts，也就是“内联格式化上下文”。
+ 作用
 - 水平居中： 当一个块元素要在环境水平居中时候，设置其为inline-block则会在外层产生IFC，通过text-align:center则可以使其水平居中
  ```html
  <style>
    .box{
      width: 100px;
      height:100px;
      background: rosybrown;
      text-align:center;
    }

    .child{
      width: 80px;
      height: 50px;
      background: seagreen;
      display: inline-block;
    }
  </style>

  <div class="box">
    <div class="child">测试文本</div>
  </div>
  ```
 - 垂直居中： 创建一个IFC，用其中一个元素撑开父元素的高度，然后设置其vertical-align:middle,其他行内元素则可以在此父元素下垂直居中
 ```html
  
 ```

+ 解决img底部有间隙的问题
  - display:block;
  - vertical-align:middle; // top, bottom
  - font-size: 0; // 会造成子元素文字消失

  ## 清除浮动
  ```css
  .clearfix::after{
      content:'';
      display: block;
      clear:both;
  }
  ```