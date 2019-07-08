<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [CSS From Zero To Hero](#CSS-From-Zero-To-Hero)
  - [Flex布局](#Flex%E5%B8%83%E5%B1%80)
    - [Flex解决的问题](#Flex%E8%A7%A3%E5%86%B3%E7%9A%84%E9%97%AE%E9%A2%98)
    - [Flex的核心思想](#Flex%E7%9A%84%E6%A0%B8%E5%BF%83%E6%80%9D%E6%83%B3)
    - [Flex与常规布局的差别](#Flex%E4%B8%8E%E5%B8%B8%E8%A7%84%E5%B8%83%E5%B1%80%E7%9A%84%E5%B7%AE%E5%88%AB)
    - [Flex应用场景](#Flex%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
    - [Flex基本概念](#Flex%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5)
    - [Flex容器属性](#Flex%E5%AE%B9%E5%99%A8%E5%B1%9E%E6%80%A7)
    - [Flex项目属性](#Flex%E9%A1%B9%E7%9B%AE%E5%B1%9E%E6%80%A7)
  - [Flex demo](#Flex-demo)
    - [水平垂直居中](#%E6%B0%B4%E5%B9%B3%E5%9E%82%E7%9B%B4%E5%B1%85%E4%B8%AD)
    - [响应式导航栏](#%E5%93%8D%E5%BA%94%E5%BC%8F%E5%AF%BC%E8%88%AA%E6%A0%8F)
  - [圣杯布局](#%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80)
    - [圣杯布局概念](#%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80%E6%A6%82%E5%BF%B5)
    - [DOM结构](#DOM%E7%BB%93%E6%9E%84)
    - [圣杯布局传统方式实现](#%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80%E4%BC%A0%E7%BB%9F%E6%96%B9%E5%BC%8F%E5%AE%9E%E7%8E%B0)
  - [双飞翼布局](#%E5%8F%8C%E9%A3%9E%E7%BF%BC%E5%B8%83%E5%B1%80)
    - [双飞翼概念](#%E5%8F%8C%E9%A3%9E%E7%BF%BC%E6%A6%82%E5%BF%B5)
    - [区别于圣杯布局](#%E5%8C%BA%E5%88%AB%E4%BA%8E%E5%9C%A3%E6%9D%AF%E5%B8%83%E5%B1%80)
    - [DOM结构](#DOM%E7%BB%93%E6%9E%84-1)
  - [CSS转换](#CSS%E8%BD%AC%E6%8D%A2)
    - [概念](#%E6%A6%82%E5%BF%B5)
    - [语法](#%E8%AF%AD%E6%B3%95)
    - [2D转换](#2D%E8%BD%AC%E6%8D%A2)
    - [3D转换](#3D%E8%BD%AC%E6%8D%A2)
    - [过渡](#%E8%BF%87%E6%B8%A1)
    - [动画](#%E5%8A%A8%E7%94%BB)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# CSS From Zero To Hero

## Flex布局

### Flex解决的问题

- 为页面布局、元素间的对齐和元素空间的分配提供更有效的方案。

### Flex的核心思想

- 让容器能更改项的宽度或者高度，从而最佳地填充可用空间（主要是为了适应各种设备和屏幕大小）。**Flex容器能扩展项去填充可用的空闲空间，也能收缩项来防止项溢出。**

### Flex与常规布局的差别

- 最重要要理解的是：**Flex与常规布局（也就是那些基于垂直的块级或者基于水平的行内级元素）相比，Flex布局与方向是无关的。**

### Flex应用场景

- Flex适用于应用程序的组件和小规模布局中。

### Flex基本概念

- **容器和项**:Flex容器是包含Flex项目的块，直接包含在Flex块内的元素都是Flex项。
![container](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)
![items](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

- **Flex布局方向**:常规布局方向是基于块级和内联，而Flex则是基于`flex-flow`方向。
![flex](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

- **图中main指的是主轴的相关属性，cross指的是交叉轴（垂直于主轴）的相关属性。注意，主轴并不一定是交叉向的，这取决与`flex-direction`的属性。**

- Flex项目会沿着主轴或交叉轴进行布置。

### Flex容器属性

- `display:flex`, 定义一个flex容器，为所有的直接子元素启用flex上下文。

- `flex-direction: row(default) | row-reverse | column | column-reverse`，建立Flex的主轴，定义了Flex项的排列方向。
![flex-direction](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

- `flex-wrap: nowrap(default) | wrap | wrap | wrap-reverse`，默认情况下，felx项目会放在一行上，修改该属性可以让项目换行排列。
![flex-wrap](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

- `flex-flow: <flex-direction> || <flex-wrap>`,是两个属性的简写，一起定义容器的主轴和交叉轴，默认值是`row nowrap`

- `justify-content: flex-start(default) | flex-end | center | space-between | space-around | space-evenly`，定义了主轴方向上flex项目的对齐方式。注意：space-around和space-evenly的区别在于主轴起始和结束时的间距，around是两个相邻flex项间距的一半，evenly和flex项间距一样。
![justify-content](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

- `align-items: flex-start | flex-end | center | stretch(default) | baseline`，定义了交叉轴方向上flex项目的对齐方式。
![align-items](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

- `align-content: flex-start | flex-end | center | stretch(default) | space-between | space-around`，定义了当交叉轴有多余空间时，flex容器的行对齐方式。当flex项目只有一行的时候，不生效。
![align-conter](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)

### Flex项目属性

- `order: <integer>(default 0)`，默认情况下，flex项目按源顺序排列，`order`属性可以控制他们在容器中出现的顺序。
![order](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)

- `flex-grow: <number>(default 0,negative numbers are invalid)`，定义了flex项目在必要时的伸展能力，接受一个作为比例的无单位值，指定项目在flex容器中应该占用多少可用空间。如果所有项目都设置为1，那么容器剩余的空间会平均分配给所有子元素，如果其中一个子元素的值为2，那么它占用的空间是其他元素空的两倍。
![flex-grow](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)

- `flex-shrink: <number>(defalut 1)`，定义了flex项目在必要时的收缩能力。

- `flex-basis: <length> | auto(default) | content`，定义了flex项目在主轴方向上的初始大小。`length`可以是一个长度单位。`auto`关键字的关键字意思是"查看我的宽度或高度属性"。`content`关键字的意思是"根据项目的内容调整大小"，但支持不好，不建议使用。如果设置为0，则不考虑内容周围的额外空间。如果设置为auto，则根据其flex-grow值分配额外空间。
![flex-basic](https://www.w3.org/TR/css-flexbox-1/images/rel-vs-abs-flex.svg)

- `flex: none | [<'flex-grow'> <flex-shrink>? || <flex-basic> ]`,这是三个属性组合的简写。其中只有flex-grow是必须的。三个属性对应的默认值是 0 1 auto.建议使用这种简写属性

- `align-self: auto | flex-start | flex-end | center | baseline | stretch`，flex项目可以通过该属性对`align-item`属性进行重写。
![align-self](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)

- **注意：`float`，`clear`, `vertical-align`对flex项目无效**

## Flex demo

### 水平垂直居中

- 原理：flex项目设置`maring: auto`会吸收额外的空间。因此设置auto的外边距会让flex项目完美的定位在两个轴的中心。


### 响应式导航栏

- 原理：媒体查询对flex容器进行修改`justify-content`和`flex-direction`的值。

## 圣杯布局

### 圣杯布局概念

1. **两侧宽度固定，中间宽度自适应。**
2. 中间部分在DOM结构上优先，以便先渲染。
3. 允许三列中的任意一列成为最高列
4. 只需要使用一个额外的`div`标签

### DOM结构

```html
<div class="container">
  <div class="column" id="center">主体部分</div>
  <div class="column" id="left">左边内容</div>
  <div class="column" id="right">右边内容</div>
</div>
```

### 圣杯布局传统方式实现

1. `container`类容器预留左右内边距
2. `container`类中的的三列都变为左浮动
3. `center`类主要内容的宽度设置为100%
4. `left`左边内容的负左外边距设置为-100%
5. `left`左边内容`position`为`relative`,将其`left`设置为相应的宽度
6. `right`右边内容的负右边距设置为相应的宽度

![holy grail](https://upload-images.jianshu.io/upload_images/9397803-e964c6f980b5da16.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/540/format/webp)

## 双飞翼布局

### 双飞翼概念

1. **两侧宽度固定，中间宽度自适应。**
2. 中间部分在DOM结构上优先，以便先渲染。
3. 允许三列中的任意一列成为最高列
4. 只需要使用一个额外的`div`标签

### 区别于圣杯布局

- DOM结构的区别：用`container`包裹住`center`，另外将`column`类移动到`container`类中。

- CSS区别：让`container`宽度为100%，让`center`预留出左右内容宽度，让右内容的负外边距为相应宽度。

### DOM结构

```html
<div class="container column">
  <div id="center">
    主体内容
  </div>
</div>
<div class="column" id="left">左边内容</div>
<div class="column" id="right">右边内容</div>
```

## CSS转换

### 概念

- Transform可以让一个坐标系统中变形。

### 语法

- `transfrom: none | 多个转换函数`，默认值是`none`。

### 2D转换

- rotate(),旋转,`transform: rotate(deg)`
- translate(), 平移,`transform: translate(x, y),translateX(length),translateY(length)`
- scale()，缩放, `transfrom: scaleX(number), scaleY(number), scale(x, y)`
- skew()，斜切, `skewX(deg), skewY(deg), skew(x, y)`
- matrix()，矩阵，混合转换

### 3D转换

![3d](https://image-static.segmentfault.com/268/357/268357742-5d1daf8d70482_articlex)

- rotate3d(),`rotateX(),rotateY(),rotateZ(),rotate3d(x, y, z, angle)`
- translate3d(),`translateZ(), translate3d(x, y, z)`
- scale3d(), `scaleZ(), scale3d(x, y, z)`
- matrix3d()
- perspective()

- transfrom-origin: x y z;，更改元素的转换中心

### 过渡

- 让CSS的属性值在一定的时间区间内平滑地过渡。

- `transition-property: none | all(default) | property`,设置对象中参与过渡的属性

- `transition-duration: time`，持续时间

- `transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out`，设置动画的贝塞尔曲线

- `transition-delay`，设置对象延迟过渡的时间

- `transition: property time function delay`，缩写

### 动画

- `animation-name: keyframename`,设置对象应用的动画名称

- `animation-duration: time`，设置动画的持续时间

- `animation-timing-function`,设置动画的贝塞尔曲线

- `animation-delay`,设置动画的延迟时间

- `animation-iteration-count: number| infinite`,设置动画的循环次数

- `animation-direction： normal | reverse | alternate | alternate-reverse | initial | inherit`,设置对象在循环中是否反向运动。

- `animation-fill-mode：none|forwards|backwards|both`，设置动画不播放的时候，元素的样式

- `animation-play-state: pause|running`，设置动画暂停

- `animation`,缩写，只有name和duration是必须的

- `@keyframes`关键帧，通过逐步改变从一个CSS样式设定到另一个。
```css
@Keyframe animationName {
  keyframes-selector {
    css-styles;
  }
}
```
- `animationName`，是动画的名称。
- `keyframes-selector: 0-100%, from, to`，动画的持续时间
- `css-styles: 一个或多个合法的CSS样式`

- `will-change`,触发GPU加速