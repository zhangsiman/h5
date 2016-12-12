### 什么是 Canvas?
HTML5 <canvas> 元素用于图形的绘制，通过脚本 (通常是JavaScript)来完成.

<canvas> 标签只是图形容器，您必须使用脚本来绘制图形。

可以通过多种方法使用Canva绘制路径,盒、圆、字符以及添加图像。

适用于　Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 支持 <canvas> 元素.

注意: Internet Explorer 8 及更早 IE 版本的浏览器不支持 <canvas> 元素.

实例

```
<canvas id="myCanvas" width="200" height="100"
style="border:1px solid #000000;">
</canvas>
```
canvas 元素本身是没有绘图能力的。所有的绘制工作必须在 JavaScript 内部完成：

实例

```js

<script>
var c=document.getElementById("myCanvas"); //找到 <canvas> 元素:
var ctx=c.getContext("2d");//创建 context 对象：
ctx.fillStyle="#FF0000";
ctx.fillRect(0,0,150,75);//绘制一个红色的矩形
</script>
```
### Canvas - 图像

把一幅图像放置到画布上, 使用以下方法:

- drawImage(image,x,y)
```js
JavaScript:
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");
var img=document.getElementById("scream");
ctx.drawImage(img,10,10);
```
### Canvas - 渐变

渐变可以填充在矩形, 圆形, 线条, 文本等等, 各种形状可以自己定义不同的颜色。

以下有两种不同的方式来设置Canvas渐变：

- createLinearGradient(x,y,x1,y1) - 创建线条渐变

- createRadialGradient(x,y,r,x1,y1,r1) - 创建一个径向/圆渐变

当我们使用渐变对象，必须使用两种或两种以上的停止颜色。

addColorStop()方法指定颜色停止，参数使用坐标来描述，可以是0至1.

使用渐变，设置fillStyle或strokeStyle的值为 渐变，然后绘制形状，如矩形，文本，或一条线。

使用 createLinearGradient():

```js
JavaScript:
var c=document.getElementById("myCanvas");
var ctx=c.getContext("2d");

// Create gradient
var grd=ctx.createLinearGradient(0,0,200,0);
grd.addColorStop(0,"red");
grd.addColorStop(1,"white");

// Fill with gradient
ctx.fillStyle=grd;
ctx.fillRect(10,10,150,80);
```
