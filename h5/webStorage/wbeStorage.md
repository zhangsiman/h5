# webStorage

HTML5 提供了两种在客户端存储数据的新方法：

- localStorage - 没有时间限制的数据存储(ie 不兼容)

- sessionStorage - 针对一个 session 的数据存储

### localStorage 属性
```js
localStorage.length
```

### localStorage 方法

localStorage 方法存储的数据没有时间限制。第二天、第二周或下一年之后，数据依然可用。

-  保存数据：localStorage.setItem(key,value);
- 读取数据：localStorage.getItem(key);
- 删除单个数据：localStorage.removeItem(key);
- 删除所有数据：localStorage.clear();
- 得到某个索引的key：localStorage.key(index);

对用户访问页面的次数进行计数实例：
```js
<script type="text/javascript">
if (localStorage.pagecount)
  {
  localStorage.pagecount=Number(localStorage.pagecount) +1;
  }
else
  {
  localStorage.pagecount=1;
  }
document.write("Visits "+ localStorage.pagecount + " time(s).");
</script>
```
### sessionStorage 方法

sessionStorage 方法针对一个 session 进行数据存储。当用户关闭浏览器窗口后，数据会被删除。

对用户在当前 session 中访问页面的次数进行计数：

```js
<script type="text/javascript">
if (sessionStorage.pagecount)
  {
  sessionStorage.pagecount=Number(sessionStorage.pagecount) +1;
  }
else
  {
  sessionStorage.pagecount=1;
  }
document.write("Visits "+sessionStorage.pagecount+" time(s) this session.");
</script>
```

### 实例　利用JSON 存储联系人信息

都只有2个字段，姓名和手机号码，如果要存入更为丰富的联系人信息，比如公司名称、家庭地址等，如何实现呢？Web Storage不是只能处理字符串吗？此时，可以利用JSON的stringify()方法，将复杂对象转变成字符串，存入Web Storage中；当从Web Storage中读取时，可以通过JSON的parse()方法再转换成JSON对象；
如下简单演示增加了公司属性的联系人保存JS代码：

复制代码代码如下:

```js
//保存数据
function save(){
var contact = new Object;
contact.user_name = document.getElementById("user_name").value;
contact.mobilephone = document.getElementById("mobilephone").value;
contact.company = document.getElementById("company").value;
var str = JSON.stringify(contact);
localStorage.setItem(contact.mobilephone,str);
loadAll();
}
//将所有存储在localStorage中的对象提取出来，并展现到界面上
function loadAll(){
var list = document.getElementById("list");
if(localStorage.length>0){
var result = "<table border='1'>";
result += "<tr><td>姓名</td><td>手机</td><td>公司</td></tr>";
for(var i=0;i<localStorage.length;i++){
var mobilephone = localStorage.key(i);
var str = localStorage.getItem(mobilephone);
var contact = JSON.parse(str);
result += "<tr><td>"+contact.user_name+"</td><td>"+contact.mobilephone+"</td><td>"+contact.company+"</td></tr>";
}
result += "</table>";
list.innerHTML = result;
}else{
list.innerHTML = "目前数据为空，赶紧开始加入联系人吧";
}
}
```
[参考](http://www.jb51.net/html5/70029.html)
