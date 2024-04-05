- 黑暗模式
    
    ```css
    @media (prefers-color-scheme: light) {
    prefers-color-scheme CSS 媒体特性用于检测用户是否有将系统的主题色设置为亮色或者暗色。
    ```
    

- :root 是 CSS 中的伪类选择器，用于选择文档的根元素。在 HTML 中，根元素是 <html> 元素，通过这种方式定义全局的 CSS 变量，var() 函数来引用全局变量
- "rem" 是 CSS 中的单位之一，它表示相对于根元素（即 <html> 元素）的字体大小的倍数
    
    默认情况下，浏览器的根元素字体大小通常是 16 像素 1rem = 16px
    
    rem 单位在不同设备和屏幕尺寸下可以自动适应和缩放
    
- z-index 约大越层级越靠前
- "transition: all .50s ease;" 表示当元素属性发生变化时，将以0.5秒的持续时间和平滑的速度曲线进行过渡效果
- a:first-child
    
    伪类选择器之一，它选择某个元素的父元素的第一个子元素
    
    后代选择器（Descendant Selector）使用空格
    
    子代选择器（Child Selector）使用大于号（>）来表示，它选择指定元素的直接子元素
    
- iconfont 与 文字水平对齐 :   `vertical-align: middle;`
- `height: 100vh;` 设置元素的高度为视口高度的百分比
- 文字上下不够紧凑：line-height: 1.2;

#menu-icon

```css
#menu-icon {
    color: var(--text-color);
    font-size: 30px;
    cursor: pointer;
    z-index: 10001;
    /* todo */
    display: none;
}
```

```css
.home {
    position: relative;
    height: 100vh;
    width: 100%;
    /* 定义了一个线性渐变背景，从左到右渐变，这个渐变背景会覆盖在背景图像上方 */
    background-image: linear-gradient(to left, rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.3)), url(../img/Background.png);
		/* 使用"cover"值时，背景图像将被缩放并调整大小，以便完全覆盖元素的背景区域，可能会裁剪部分图像 */
    background-size: cover;
    /* 将会展示图片 中间靠下的部分 */
    background-position: bottom center;
    display: flex;
}
```

font-weight 使用 500 600 700 更好看

```css
标题使用
font-size: 33px;
font-weight: 700;

a标签
font-size: var(--p-font);
font-weight: 500;
color: #ffffffab;
```

a 标签为什么无法 translateX：inline-block

<a> 标签是一个行内元素（display: inline;），这意味着它会根据文本流水平排列，并且不会对宽度和高度产生影响。而 translateX 属性只对块级元素起作用

```css
grid-template-columns: repeat(auto-fit, minmax(150px, auto));
repeat()函数用于重复列大小的模式。它接受两个参数：第一个参数指定模式应该重复的次数，第二个参数定义列大小的模式。
auto-fit被用作第一个参数。这意味着网格将根据网格容器中的可用空间自动调整列的数量。它会尽量在容器内适应尽可能多的列。
minmax()函数用于指定可接受的大小范围，其中第一个参数是最小值，第二个参数是最大值。在这里，列的最小宽度被设置为150像素，而最大宽度被设置为自动。这意味着列的宽度可以在150像素和自动之间自由调整。

```

box-sizing: border-box;

不会把 padding 和 border

backdrop-filter: blur(35px); 将背景模糊化，模糊半径为35像素

text-transform: uppercase;

letter-spacing: 6px;

按钮做质感

```css
    border: 2px solid transparent;
    border-radius: 5px;
    transition: all .50s ease;
    cursor: pointer;
    
.btn:hover {
    transform: translateX(10px);
    border: 2px solid var(--text-color);
    background-color: transparent;
    color: var(--text-color);
}
```

当应用 object-fit: cover; 时，元素将会被拉伸或缩放以填充其容器，并保持其原始的宽高比。

brightness(70%) 表示将元素的亮度设置为 70%。

```css
.box img {
    height: 100%;
    width: 100%;
    object-fit: cover;
    border-radius: 10px;
    filter: brightness(70%);
    transition: all .3s cubic-bezier(.499, .05, .55, .95);
    will-change: filter;
    display: block;
}

transition: all .3s cubic-bezier(.499, .05, .55, .95);：为图片的所有属性添加过渡效果，过渡时间为0.3秒，使用贝塞尔曲线函数来定义过渡的速度变化。
will-change: filter;：告诉浏览器该元素的 filter 属性将要发生变化，以优化性能。

.box img:hover {
    filter: brightness(90%) hue-rotate(50deg);
    transform: scale(1.04);
    cursor: pointer;
}
并对色调进行 50 度的旋转。这将使图片变得更亮，并且添加一些色调的变化。
```

grid 布局常用：    gap: 1rem;

    display: inline-flex; inline-flex允许元素在水平方向上具有弹性布局的能力，同时保持内联元素的特性，即可以与其他元素在同一行上显示。

@media (max-width: 1700px) { 当视口宽度小于或等于 1700 像素时，媒体查询中的样式规则将会生效

```css
menu.onclick = () => {
    menu.classList.toggle('bx-x');
    navbar.classList.toggle('open')
}
```

toggle 方法有两种可能的行为：

如果元素的 class 列表中已经包含了指定的类，则 toggle 方法会将该类从 class 列表中移除，并返回 false。
如果元素的 class 列表中不包含指定的类，则 toggle 方法会将该类添加到 class 列表中，并返回 true。

当浏览器解析 HTML 文档时，按照从上到下的顺序逐步加载和渲染页面内容。如果将 <script> 标签放在 <head> 标签内，那么在执行 JavaScript 代码之前，浏览器会阻塞页面的加载和渲染，直到 JavaScript 代码被完全下载、解析和执行完毕。这可能导致页面出现白屏或加载延迟的情况，给用户带来不好的体验。