# img-center-test
集合目前能想到的居中图片的做法并区分



## 通过 `margin` 实现

### 实现方式

将 `<img>`  包在 `<div>` 中,  然后设置 `<div>` 的样式如下:

```css
div {
    width: 1000px; // 图片大小
    margin: 0 auto;
}
```

### 效果

1. 当视窗宽度<u>大于</u> `<div>` 宽度时,  图片完全显示,  且图片呈现为居中状态
2. 当视窗宽度<u>小于等于</u> `<div>` 宽度时候, 图片部分显示,  且显示的部分也不是图片中间部分



## 通过 `text-align` 实现

### 实现方式

通过设定 `<img>` 父元素的 `text-align` css 样式为 `center` 实现:

```css
body {
    text-align: center;
}
```

### 效果

1. 当视窗宽度<u>大于</u> `<img>` 宽度时,  图片完全显示,  且图片呈现为居中状态
2. 当视窗宽度<u>小于等于</u> `<img>` 宽度时候, 图片部分显示,  且显示的部分也不是图片中间部分



## 通过 `flex ` 实现

### 实现方式

将 `<img>` 父元素设定为 `flex box`实现,  具体 css 如下: 

```css
body {
    display: flex;
    justify-content: center;
}
```

### 效果

1. 当视窗宽度<u>大于</u> `<img>` 宽度时,  图片完全显示,  且图片呈现为居中状态
2. 当视窗宽度<u>小于等于</u> `<img>` 宽度时候, 图片依然完全显示,  但是图片会<u>等比例缩小</u>



## 通过 `background` 实现

### 实现方式

图片设置为 `div` 的背景图片,  并将其设置为居中,  具体 css 如下:

```css
div {
    width: 100%; // 整个视窗的宽度
    height: 650px; // 图片的高度
    background: url(./product3.jpg) no-repeat center
}
```

### 效果

1. 当视窗宽度<u>大于</u> `<img>` 宽度时,  图片完全显示,  且图片呈现为居中状态
2. 当视窗宽度<u>小于等于</u> `<img>` 宽度时候, 图片部分显示,   <u>显示部分始终为图片的中间部分!</u>



## 通过 `position` 实现

### 实现方式

将图片左移自身宽度一半的距离,  然后在向右移动视窗一半的距离,  具体 css 如下:

```css
img {
	margin-left: -500px;
	position: relative;
	left: 50%;
}
```

### 效果

1. 当视窗宽度<u>大于</u> `<img>` 宽度时,  图片完全显示,  且图片呈现为居中状态
2. 当视窗宽度<u>小于等于</u> `<img>` 宽度时候, 图片部分显示,   <u>显示部分始终为图片的中间部分!</u>



## 总结

就目前来看,  实现图片居中的最好方式, 是使用 `position` 或 `background` 实现!