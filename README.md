# JSgo

数据类型  typeof   document.geyElementByid///(动态的)  querySelector(静态的)

git status  查看当前状态
git  add .把工作区的代码存到暂存区
git commit -m '可以写中文'
 git push origin master

5-25
重新认识了一个新的属性
document.getElementByTagName  
他可以获取HTML元素的列表
也可以去获取文档中的一个特定元素比如 获取某行的第三个段落  var a = document.getElementByTagName('p')[2];

disabled  是一个禁用的属性禁止去操作

取模 取余 可以用在各行变色上

a%b = 余数  或者  i%2 == 0  进行各行变色

			for循环

				for(var i=0;i<10;i++){
			 		要循环执行的代码
			 	}
			 	for(初始化变量;判断条件;变量变化){
			 		要循环执行的代码
			 	}
连接符 + 
两个数字叫相加
一边是字符串就进行连接

this 关键字
 函数之外的this  指的是window  
 函数之内的this  1.直接调用   2. 调用该事件 函数的元素对象

 个人对this的新认识 

 	for(var i=0;i<lis.length;i++){
				lis[i].index = i;
				lis[i].onclick = function(){
				console.log(this.index)
				divs[this.index].style.background = 'red';
				}
			}
这里的index就是属于个人自定义的属性 可以变成任何新的代名词
for循环中，当i =0时,lis[0].index = 0;
下面的function 中的this指向就是lis[0],而打印输出的内容就是0.  div[this.index]就是点击第0个div的时候背景颜色变红（也就是li是1的时候）
JS中是一次往下循环的
	for(var i=0;i<lis.length;i++){
				lis[i].onclick = function(){
					//1.清除所有
					for(var i=0;i<lis.length;i++){
						lis[i].style.background = '';
					}
					this.style.background = 'red';
				}
			}
上面的函数也是this的指向问题。一次循环往下走。首先将this指向的style.background清理为空 然后再给this指向的li进行赋值变色。

var prev = lis[0];
null:空对象，明确知道变量要存对象，暂时没有可存的，可以先赋值null
再循环之后要进行这个prev = this;

我去，无语了，更新了github居然没有绿，很心痛。原来是邮箱出现了错误。
在github提交了代码或者总结之后出现不绿的情况，很有可能是你的本地邮箱跟你github的邮箱不一致导致的。
解决的办法是 打开本地的git bash，然后直接输入
git config user.email
查看你的本地配置邮箱，看看是否和github上面绑定的邮箱一致，如果不一致则更改一下。
git config --global user.email "hello@163.com"
然后再次输入  git config user.email
看是否与你刚才输入的那个邮箱的地址一样。之后再提交代码，格子就会显绿了。

5-26 总结
for循环套用for循环
	for(var i=0;i<10;i++){
				console.log('外:'+i)
				for(var j=0;j<10;j++){
					console.log('内'+j)
				}
			}
在循环的套用中需要去改变循环中的变量

鼠标的移入移出（mouseover  mouseout）
				mouseover
			 		鼠标从元素外移入元素内，从元素内移入子元素，都会触发
			 		
			 	mouseout
			 		鼠标从元素内移到元素外，从元素内移入子元素，都会触发
				mouseenter
			 		鼠标从元素外移入元素内触发
			 		
			 	mouseleave
			 		鼠标从元素内移到元素外触发
总结：mouseover mouseout mouseenter  mouseleave  这四个都是鼠标的移入移出，但是他们是有区别的，mouserover和mouserout当两个大小不同和盒子重叠在一块。鼠标只要移入其中一个就会显示鼠标移入，鼠标向重叠部分移入就是显示在大盒子里移出，移入小盒子里。小盒子里出来就会显示移出，移入大盒子。
mouseenter  mouseleave 他们就与mouseover mouseout不同，他们是只要你鼠标移入就会显示mouseenter，当你鼠标进入盒子的重叠部分时候，也不会出现鼠标移出的字样，而是一直都在大盒子里。当你在小盒子里的时候，你鼠标移入会提示，鼠标移入，但是当你小盒子被大盒子包围的时候，你鼠标已经移出小盒子的范围，也不会出现鼠标移出的字样，只要你的鼠标移出到大盒子外的时候才会报出鼠标移出。

隔行变色的问题（多种解决的方案）
1.可以利用之前的if-取模
	if（i%2）{
		XXX.className='颜色';
	}else{
		XXX.className='颜色';
	}
2.利用索引值得方法
lis[i].index = i;（索引指的就是i）
3.自定义属性  存数据，私有化
lis[i].color = lis[i].className;

	lis[i].check = false;
4.鼠标移入移出li

前面的总结
获取元素  id  class  tag  css（querySelector）
id  css  获取的是静态的
tag  class  获取的是动态的

属性的操作  .  []  行间 可读可写

div.style.height='200px';
div.style['background-color']='red';

if(){
	
}else{
	
}
if(){
	
}else if(){
	
}else if(){
	
}
for 循环
for(var i=0;i<length;i++){
	
}
this 的指向问题
鼠标移入移出的他们的区别与不同