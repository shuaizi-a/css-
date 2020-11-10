## viewport缩放适配
```html
<!-- content属性值 :
     width:可视区域的宽度，值可为数字或关键词device-width
     height:同width
     intial-scale:页面首次被显示是可视区域的缩放级别，取值1.0则页面按实际尺寸显示，无任何缩放
     maximum-scale=1.0, minimum-scale=1.0;可视区域的缩放级别，
     maximum-scale用户可将页面放大的程序，1.0将禁止用户放大到实际尺寸之上。
     user-scalable:是否可对页面进行缩放，no 禁止缩放 -->
<meta id="viewport" name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">

<script>
  //  html字体随页面大小改变
  function computedREM() {
    let HTML = document.documentElement,
        winW = HTML.clientWidth;
    HTML.style.fontSize = winW / 750 * 100 + 'px' // 750设计稿宽度, 100字体大小
  }
  computedREM()
  window.addEventListener('resize', computedREM)
</script>

<!-- 总结
REN响应式布局开发思路
第一步： 拿到设计稿后（一般750px）, 我们设定一个初始的 REM 和 PX 的换算比例（一般设置 1REM = 100PX, 方便后期换算）
第二个：测量出设计稿的元素尺寸，在编写样式的时候 其全部转换为 REM 的单位（除于100） => 100% 还原设计稿
第三步：编写一段js，获取当前设备的宽度， 让其除于设计稿的宽度750，再乘以初始换算比例100，计算出当前设备下 1REM 等于多少像素
第四步：项目中主体布局还是以 REM 为主，部分效果可以基于 flex 布局来完成 需要样式微调基于 @meida 来完成 -->
```

## 媒体查询
```css

```

## 单位
```html
px 固定单位
em 相对父元素的字体的大小
%  相对于父元素的尺寸
rem 根元素字体的大小
vw 相对于视口 1vw = 1/100 * 视口宽

```