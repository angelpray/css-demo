<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [CSS From Zero To Hero](#css-from-zero-to-hero)
  - [Flex布局](#flex%E5%B8%83%E5%B1%80)
    - [Flex解决的问题](#flex%E8%A7%A3%E5%86%B3%E7%9A%84%E9%97%AE%E9%A2%98)
    - [Flex的核心思想](#flex%E7%9A%84%E6%A0%B8%E5%BF%83%E6%80%9D%E6%83%B3)
    - [Flex与常规布局的差别](#flex%E4%B8%8E%E5%B8%B8%E8%A7%84%E5%B8%83%E5%B1%80%E7%9A%84%E5%B7%AE%E5%88%AB)
    - [Flex应用场景](#flex%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF)
    - [Flex基本概念](#flex%E5%9F%BA%E6%9C%AC%E6%A6%82%E5%BF%B5)
    - [Flex容器相关属性](#flex%E5%AE%B9%E5%99%A8%E7%9B%B8%E5%85%B3%E5%B1%9E%E6%80%A7)

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

- **容器和项**:Flex容器是包含Flex项目的块，直接包含在Flex块内的元素都是Flex项
![container](https://css-tricks.com/wp-content/uploads/2018/10/01-container.svg)
![items](https://css-tricks.com/wp-content/uploads/2018/10/02-items.svg)

- **Flex布局方向**:常规布局方向是基于块级和内联，而Flex则是基于`flex-flow`方向。
![flex](https://css-tricks.com/wp-content/uploads/2018/11/00-basic-terminology.svg)

- **图中main指的是主轴和主尺寸，cross指的是副轴和副尺寸**

- Flex项目会沿着主轴（从主轴开始到主轴结束）或横轴（从主轴开始到横轴结束）进行布置。

### Flex容器相关属性

- `display:flex`, 定义一个flex容器，为所有的直接子元素启用flex上下文。

- `flex-direction: row(default) | row-reverse | column | column-reverse`，建立Flex的主轴，定义了Flex项的排列方向。
![flex-direction](https://css-tricks.com/wp-content/uploads/2018/10/flex-direction.svg)

- `flex-wrap: nowrap(default) | wrap | wrap | wrap-reverse`，默认情况下，felx项目会放在一行上，修改该属性可以让项目换行排列。
![flex-wrap](https://css-tricks.com/wp-content/uploads/2018/10/flex-wrap.svg)

- `flex-flow: <flex-direction> || <flex-wrap>`,是两个属性的简写，一起定义容器的主轴和横轴，默认值是`row nowrap`

- `justify-content: flex-start(default) | flex-end | center | space-between | space-around | space-evenly`，定义了主轴方向上flex项目的对齐方式。
![justify-content](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

- `align-items: flex-start | flex-end | center | stretch | baseline`，定义了横轴（垂直于主轴）方向上flex项目的对齐方式。
![align-items](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

- `align-content: flex-start | flex-end | center | stretch | space-between | space-around`，定义了当横轴有多余空间时，flex容器的行对齐方式。当flex项目只有一行的时候，不生效。
![align-conter](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)

- 

