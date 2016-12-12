# Navigator 对象

----Navigator 对象包含有关浏览器的信息。

Navigator 对象属性

- appCodeName	返回浏览器的代码名。
- appMinorVersion	返回浏览器的次级版本。
- appName	返回浏览器的名称。
- appVersion	返回浏览器的平台和版本信息。
- browserLanguage	返回当前浏览器的语言。
- cookieEnabled	返回指明浏览器中是否启用 cookie 的布尔值。
- cpuClass	返回浏览器系统的 CPU 等级。
- onLine	返回指明系统是否处于脱机模式的布尔值。
- platform	返回运行浏览器的操作系统平台。
- systemLanguage	返回 OS 使用的默认语言。
- userAgent	返回由客户机发送服务器的 user-agent 头部的值。
- userLanguage	返回 OS 的自然语言设置。

## 进度条代码
```js

<ul class="lanren">
	<li>red <span id="title">0</span>
		<div class="scale_panel">
			<span class="r">100</span>0
			<div class="scale" id="bar">
				<div></div>
				<span id="btn"></span>
			</div>
		</div>
	</li>
</ul>
<script>
var scale = function (btn,bar,title){
	this.btn=document.getElementById(btn);
	this.bar=document.getElementById(bar);
	this.title=document.getElementById(title);
	this.step=this.bar.getElementsByTagName("div")[0];
	this.init();
};
scale.prototype={
	init:function (){
		var f=this,g=document,b=window,m=Math;
		f.btn.onmousedown=function (e){
			var x=(e||b.event).clientX;
			var l=this.offsetLeft;
			var max=f.bar.offsetWidth-this.offsetWidth;
			g.onmousemove=function (e){
				var thisX=(e||b.event).clientX;
				var to=m.min(max,m.max(-2,l+(thisX-x)));
				f.btn.style.left=to+'px';
				f.ondrag(m.round(m.max(0,to/max)*100),to);
				b.getSelection ? b.getSelection().removeAllRanges() : g.selection.empty();
			};
			g.onmouseup=new Function('this.onmousemove=null');
		};
	},
	ondrag:function (pos,x){
		this.step.style.width=Math.max(0,x)+'px';
		this.title.innerHTML=pos+'%';
	}
}
new scale('btn','bar','title');
</script>
```
