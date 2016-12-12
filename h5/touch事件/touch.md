# touch 事件

- touchstart事件：当手指触摸屏幕时候触发，即使已经有一个手指放在屏幕上也会触发。

- touchmove事件：当手指在屏幕上滑动的时候连续地触发。在这个事件发生期间，调用preventDefault()事件可以阻止滚动。

- touchend事件：当手指从屏幕上离开的时候触发。

- touchcancel事件：当系统停止跟踪触摸的时候触发。关于这个事件的确切出发时间，文档中并没有具体说明，咱们只能去猜测了。

### 三个用于跟踪触摸的属性。

　- 　touches：表示当前跟踪的触摸操作的touch对象的数组。

　- 　targetTouches：特定于事件目标的Touch对象的数组。

　- 　changeTouches：表示自上次触摸以来发生了什么改变的Touch对象的数组。


### 每个Touch对象包含的属性如下。


　- 　clientX：触摸目标在视口中的x坐标。

　- 　clientY：触摸目标在视口中的y坐标。

　- 　identifier：标识触摸的唯一ID。

　- 　pageX：触摸目标在页面中的x坐标。

　- 　pageY：触摸目标在页面中的y坐标。

　- 　screenX：触摸目标在屏幕中的x坐标。

　- 　screenY：触摸目标在屏幕中的y坐标。

　- 　target：触目的DOM节点目标。


## 移动端touch 事件（封装事件）

### 滑动事件
- swipe
- swipeLeft
- swipeRight
- swipeUp
- swipeDown

### 点击事件

- doubleTap
- tap
- singleTap
- longTap

### 需要引入封装好的　js包

```js
<script src="js/zepto.min.js"></script>

<script src="js/zepto.touch.js"></script>
