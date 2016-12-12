# swiper
### Swiper常用于移动端网站的内容触摸滑动

Swiper是纯javascript打造的滑动特效插件，面向手机、平板电脑等移动终端。

Swiper能实现触屏焦点图、触屏Tab切换、触屏多图切换等常用效果。
### 1.首先加载插件，需要用到的文件有swiper.min.js和swiper.min.css文件。
 <link rel="stylesheet" href="path/to/swiper.min.css">
 <body>
     ...
     <script src="path/to/swiper.min.js"></script>
 </body>
### 基本教程

```html
<!-- //html 内容 -->
<div class="swiper-container">
    <div class="swiper-wrapper">
        <div class="swiper-slide">Slide 1</div>
        <div class="swiper-slide">Slide 2</div>
        <div class="swiper-slide">Slide 3</div>
    </div>
    <!-- 如果需要分页器 -->
    <div class="swiper-pagination"></div>

    <!-- 如果需要导航按钮 -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>

    <!-- 如果需要滚动条 -->
    <div class="swiper-scrollbar"></div>
</div>
<!-- 导航等组件可以放在container之外 -->

<!-- 初始化Swiper：最好是挨着</body>标签 -->
<script>   
window.onload = function() {     
  var mySwiper = new Swiper ('.swiper-container', {
    direction: 'vertical',
    loop: true,

    // 如果需要分页器
    pagination: '.swiper-pagination',

    // 如果需要前进后退按钮
    nextButton: '.swiper-button-next',
    prevButton: '.swiper-button-prev',

    // 如果需要滚动条
    scrollbar: '.swiper-scrollbar',
  })   
}     
  </script>
```
### api　教程做法

```html  
<body>
<script src="js/swiper-3.3.1.min.js"></script>
<div class="swiper-container">
  <div class="swiper-wrapper">
    <div class="swiper-slide">slider1</div>
    <div class="swiper-slide">slider2</div>
    <div class="swiper-slide">slider3</div>
  </div>
</div>
<script>
var mySwiper = new Swiper('.swiper-container', {
	autoplay: 1000,//可选选项，自动滑动
})
</script>

</body>
```
#### 常用选项
- autoplay
   自动切换的时间间隔（单位ms），不设定该参数slide不会自动切换。
- grabCursor
  设置为true时，鼠标覆盖Swiper时指针会变成手掌形状，拖动时指针会变成抓手形状。（根据浏览器形状有所不同）
- pagination
  分页器容器的css选择器或HTML标签。分页器等组件可以置于container之外，不同Swiper的组件应该有所区分，如#pagination1，#pagination2。
  pagination参数----类型：string or HTML Element默认：null举例： .swiper-pagination

  ```js
  var mySwiper = new Swiper('.swiper-container',{
      pagination : '.swiper-pagination',
      //pagination : '#swiper-pagination1',
    })
```
- loop
    设置为true 则开启loop模式。loop模式：会在wrapper前后生成若干个slides让slides看起来是衔接的，用于无限循环切换。
    loop模式在与free模式同用时会产生抖动，因为free模式下没有复制slide的时间点。
    loop参数

    类型：boolean默认：false举例： true
###  effect
    slide的切换效果，默认为"slide"（位移切换），可设置为"fade"（淡入）"cube"（方块）"coverflow"（3d流）"flip"（3d翻转）。
    - effect : 'fade',
－－－　h5.yiq
