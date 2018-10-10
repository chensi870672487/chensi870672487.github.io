# 面试题：
#### 1.说一下你对闭包的理解，闭包的作用，测试闭包理解的两个面试题
```
    var name = "The Window";
    var object = {
    	name: "My Object",
    	getNameFunc: function() {
			return function() {
				return this.name;
			    };
    	    }
    	};
    alert(object.getNameFunc()());
    
```
```
    var name = "The Window";

　　var object = {
　　　　name : "My Object",
　　　　getNameFunc : function(){
　　　　　　var that = this;
　　　　　　return function(){
　　　　　　　　return that.name;
　　　　　　};
　　　　}
　　};

　　alert(object.getNameFunc()());
```

#### 2.有两个关于this指向的面试题
#### 3.link和@import的区别
#### 4.Vue生命周期钩子函数说出三个，其中获取数据在哪个函数中
#### 5.Vue监听用什么，cumputed和method的区别
#### 6.前后端完全分离，前端的跨域，权限分配如何完成，搭建环境等一系列问题
#### 7.组件之间如何传递数据
#### 8.vue路由
### 9.工作中用到的CSS3，H5
#### 10.说一下你在工作中遇到的难题，是如何解决的
#### 11.数组去重方法
#### 12.事件委托（事件代理）机制理解
#### 13.居中（不知宽高）
#### 14.js中有哪些异步？并回答下面返回结果
```
var i=0;
(function(){
    window.setTimeout(function(){
        i++
    },1)
}();
var last=i++|2;
console.log(last);
```
#### 15、正则断言
## 备战
1、padding、margin设置一个百分比数值，这个百分比是相对于谁计算的？（百分数是相对于父元素的width计算的）

2、css值复制指的是？
- 如果缺少左外边距的值，则使用右外边距的值。
- 如果缺少下外边距的值，则使用上外边距的值。
- 如果缺少右外边距的值，则使用上外边距的值。

3、css垂直外边距合并指？
（只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。）

4、position

- absolute：绝对定位的元素的位置相对于最近的已定位父元素(absolute、relative、fixed)，如果元素没有已定位的父元素，那么它的位置相对于<html；脱离文档流，因此不占据空间，可以和其他元素重叠【重叠的元素：元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素z-index属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）一个元素可以有正数或负数的堆叠顺序】
- relative：相对定位，未脱离文档流，相对其正常位置定位，它原本所占的空间不会改变【也就是说，它下方的元素不会上移】，其内容可以和其他元素重叠，z-index生效，相对定位元素经常被用来作为绝对定位元素的容器块。
- static：静态定位，HTML元素的默认值，即没有定位，元素出现在正常的流中，静态定位的元素不会受到top, bottom, left, right影响。
- fixed:固定定位，元素的位置相对于浏览器窗口是固定位置(即使窗口是滚动的它也不会移动)Fixed定位使元素的位置与文档流无关即脱离文档流，因此不占据空间,Fixed定位的元素和其他元素重叠,z-index生效。
例题测试：
```
检测一下你是否真正了解了position定位

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>position</title>
	<style>
		.box1{
			position: relative;
			top:100px;
			right:100px;
			width:200px;
			height:200px;
			background: green;
		}
		.box2{
			position: absolute;
			top:50px;
			right:50px;
			width:100px;
			height:100px;
			background: red;
		}
		.box3{
			position: fixed;
			bottom: 100px;
			right:100px;
			width:50px;
			height:50px;
			background: #ccc;
		}
		.box4{
			width:200px;
			height:200px;
			background: blue;
		}
	</style>
</head>
<body>
	<div class="box1">
		A
		<div class="box2">
			B
			<div class="box3">C</div>
		</div>
	</div>
	<div class="box4"></div>
</body>
</html>
```