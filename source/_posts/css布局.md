---
title: css布局
date: 2019-03-17 21:32:00
tags: css
category: css
---

## 简单的css布局技巧

1. 左右布局/左中右布局：  
  这里使用css中的flex布局可以快速简单的完成左右/左中右布局。
  HTML:   
  ```html
  <div class="wrapper">
    <div class="item"></div>
    <div class="item"></div>
    <div class="item"></div>
  </div>
  ```

  CSS:

  ```css
  .wrapper {
    display: flex;
    justify-content: space-between;
  }
  .item {
    width: 30%;
  }
  ```
  效果如下：
  ![dddd.png](https://i.loli.net/2019/03/17/5c8e4f1d71d03.png)


这个布局的重点在于flex布局和justify-content属性，有兴趣的同学可以查看[阮一峰的flex布局](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

2. 水平居中
水平居中算是很基础的布局了

HTML:
```html
<div class="text">text</div>
```

CSS:
```css
.text {
  text-algin: center
}
```
效果如下：
![屏幕快照 2019-03-17 下午9.49.42.png](https://i.loli.net/2019/03/17/5c8e5090c58b3.png)

3. 垂直居中
垂直居中的实现方案很多，这里简单的介绍我常用的两种：

HTML：
```html
<div class="wrapper">
  text
</div>
```

CSS:
```css
.wrapper {
  display: table-cell;
  vertical-align: middle;
  text-align: center;        
}
```

效果如下：

![屏幕快照 2019-03-17 下午9.56.10.png](https://i.loli.net/2019/03/17/5c8e521915de7.png)