# transform全解
## translate() 位移
```css
{
  transform:translate(x,y);
}
```
## rotate() 旋转
```css
{
  transform:rotate(100edg);
}
```

## scale缩放
```css
{
  transform:scale(x,y);
}
```

## transform-origin元素变换基点
```css
{
  transform-origin:20% 40%;
}
```

## preserve-3d 
```css
{
  transform-style: preserve-3d;
}
```

## transition 补间动画(过渡)
## keyframes 关键帧动画
```css
{
  animation: run 1s ease alternate(循环);
}

@keyframes run{
  0%{
    width:100px;
  },  
  100%{
    width: 200px;
  }
}
```
## 逐帧动画
```css
/* steps()语法 */
```
[steps详解](https://segmentfault.com/a/1190000007042048)