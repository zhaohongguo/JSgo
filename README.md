# JSgo
数据类型 typeof document.geyElementByid///(动态的) querySelector(静态的)

git status 查看当前状态 git add .把工作区的代码存到暂存区 git commit -m '可以写中文' git push origin master

# 5-25
重新认识了一个新的属性 document.getElementByTagName
他可以获取HTML元素的列表 也可以去获取文档中的一个特定元素比如 获取某行的第三个段落 var a = document.getElementByTagName('p')[2];

disabled 是一个禁用的属性禁止去操作

取模 取余 可以用在各行变色上

a%b = 余数 或者 i%2 == 0 进行各行变色

		for循环

			for(var i=0;i<10;i++){
		 		要循环执行的代码
		 	}
		 	for(初始化变量;判断条件;变量变化){
		 		要循环执行的代码
		 	}
# 连接符 +
两个数字叫相加 一边是字符串就进行连接

# this 关键字
函数之外的this 指的是window
函数之内的this 1.直接调用 2. 调用该事件 函数的元素对象

# 个人对this的新认识

for(var i=0;i<lis.length;i++){
			lis[i].index = i;
			lis[i].onclick = function(){
			console.log(this.index)
			divs[this.index].style.background = 'red';
			}
		}
这里的index就是属于个人自定义的属性 可以变成任何新的代名词 for循环中，当i =0时,lis[0].index = 0; 下面的function 中的this指向就是lis[0],而打印输出的内容就是0. div[this.index]就是点击第0个div的时候背景颜色变红（也就是li是1的时候） JS中是一次往下循环的 for(var i=0;i<lis.length;i++){ lis[i].onclick = function(){ //1.清除所有 for(var i=0;i<lis.length;i++){ lis[i].style.background = ''; } this.style.background = 'red'; } } 上面的函数也是this的指向问题。一次循环往下走。首先将this指向的style.background清理为空 然后再给this指向的li进行赋值变色。

var prev = lis[0];

# null:
空对象，明确知道变量要存对象，暂时没有可存的，可以先赋值null 再循环之后要进行这个prev = this;

我去，无语了，更新了github居然没有绿，很心痛。原来是邮箱出现了错误。 在github提交了代码或者总结之后出现不绿的情况，很有可能是你的本地邮箱跟你github的邮箱不一致导致的。 解决的办法是 打开本地的git bash，然后直接输入 git config user.email 查看你的本地配置邮箱，看看是否和github上面绑定的邮箱一致，如果不一致则更改一下。 git config --global user.email "hello@163.com" 然后再次输入 git config user.email 看是否与你刚才输入的那个邮箱的地址一样。之后再提交代码，格子就会显绿了。

# 5-26 总结
for循环套用for循环 for(var i=0;i<10;i++){ console.log('外:'+i) for(var j=0;j<10;j++){ console.log('内'+j) } } 在循环的套用中需要去改变循环中的变量

鼠标的移入移出（mouseover mouseout） mouseover 鼠标从元素外移入元素内，从元素内移入子元素，都会触发

		 	mouseout
		 		鼠标从元素内移到元素外，从元素内移入子元素，都会触发
			mouseenter
		 		鼠标从元素外移入元素内触发
		 		
		 	mouseleave
		 		鼠标从元素内移到元素外触发
# 总结
mouseover mouseout mouseenter mouseleave 这四个都是鼠标的移入移出，但是他们是有区别的，mouserover和mouserout当两个大小不同和盒子重叠在一块。鼠标只要移入其中一个就会显示鼠标移入，鼠标向重叠部分移入就是显示在大盒子里移出，移入小盒子里。小盒子里出来就会显示移出，移入大盒子。 mouseenter mouseleave 他们就与mouseover mouseout不同，他们是只要你鼠标移入就会显示mouseenter，当你鼠标进入盒子的重叠部分时候，也不会出现鼠标移出的字样，而是一直都在大盒子里。当你在小盒子里的时候，你鼠标移入会提示，鼠标移入，但是当你小盒子被大盒子包围的时候，你鼠标已经移出小盒子的范围，也不会出现鼠标移出的字样，只要你的鼠标移出到大盒子外的时候才会报出鼠标移出。

image

隔行变色的问题（多种解决的方案）
1.可以利用之前的if-取模 if（i%2）{ XXX.className='颜色'; }else{ XXX.className='颜色'; } 2.利用索引值得方法 lis[i].index = i;（索引指的就是i） *3.自定义属性 * 存数据，私有化 lis[i].color = lis[i].className;

lis[i].check = false;
4.鼠标移入移出li

# 前面的总结
获取元素 id class tag css（querySelector）

id css 获取的是静态的

tag class 获取的是动态的

属性的操作 . [] 行间 可读可写

div.style.height='200px';

div.style['background-color']='red';

# if语句 
if(){

}else{

}

if----else---if---else

if(){

}else if(){

}else if(){

}

for 循环 for(var i=0;i<length;i++){

}

# this 的指向问题 

鼠标移入移出的他们的区别与不同 对我的readme进行大整理，更改了之前一团乱麻的样式。详情可以查看这个网址：https://www.dushibaiyu.com/2014/05/github_readme-md_markdown.html

# 如何在github上插入图片
1、首先把图片放到程序里。提交到Github远程仓库。

2、在浏览器进入远程Github仓库找到图片打开图片。那么当前浏览器链接就是图片地址。复制出来。

3、打开README.md 进入编辑状态。放入如下代码进入编辑框。保存即可看见效果

![image]（这必须写字要不，不显示地址，而显示图片，你们弄得时候可以把括号里的字去掉）(https://github.com/zhaohongguo/JSgo/blob/master/image/mouseover%20mouseout%20mouseenter%20%20mouseleave.png)

其中 https://github.com/zhaohongguo/JSgo/blob/master/image/mouseover%20mouseout%20mouseenter%20%20mouseleave.png 是我的图片地址。你们替换成你想显示的图片地址即可。

# 5-28
# 数据的类型
# 基础类型（简单类型）
			 		1.String,字符串  var str='123';
			 		2.Number，数字	  var  n = 1;
			 		3.Boolean，布尔值  true false
			 		4.Null，空      只有一个值
			 		5.Undefined，未定义  复合类型 ：由基本类型和复合类型组成
	Boolean，布尔值
		  		true false
		  
		  比较两边的值，如果数据类型不同，会先转成相同类型，再比较值是否相等
		   == 两边值相同返回true 不同返回false，不比较数据类型 
		  
		  !=   不同返回true 相同返回false，不比较数据类型 
		  
		   ===  两边值相同并且数据类型相同返回true 不同返回false，比较数据类型
		  !==  两边值或者数据类型有一个不相同返回true 都相同返回false，比较数据类型


	Null，空
		 		只有一个值null
		 	使用：
		 		1.想存一个对象类型的数据，暂时没有可存的，先赋值为null
		 		2.解绑用on绑定的事件函数
		 		btn.onclick = null
	Undefined,未定义
		 		只有一个值：undefined
		 		我们不会主动赋值undefined，系统会给为赋值的变量，默认值为undefined
数据类型中还有一个Object（对象）键值对：{}，无序性  数组：[],有序性


7.ES6新增的Symbol 特殊字符串  为了解决命名冲突覆盖的问题

# 循环对象
for(var  自定义 in  对象){

}
# typeof 检测数据类型
		 		返回是的数据类型字符串，小写
		 number string boolean undefined object function symbol
# 数据类型转换
		 		任意数据类型都可以转成字符串，数字，布尔值
		 	js提供三种原生转换方法
		 		String()
		 		Number()
		 		Boolean()
# 转字符串
		 		String()
		 		简单方法：''+数据    var n = ''+1;
# 转数字
		 		Number()
		 		
		 	1.字符串
		 		空字符串转成0			var str = '';
		 		忽略前后空格			var str3 = '    10    ';
		 		忽略前边的0				var str4 = '    000010    ';
		 		转不成纯数字就返回NaN		var str6 = '100px';

	console.log(typeof NaN)      number 
# 布尔值
true 1 false 0

# null
var Null = null console.log(Numner(Null)) 0

# undefined
var a; console.log(Number(a)) NaN

# object
	空数组：0
	非空数组：NaN
	键值对：NaN
# NaN
			NaN不等于任何值，包括自己 
			不可以用做比较
			isNaN()判断是否是NaN的方法
			先Number()方法，把括号里的数据转成数字类型，如果是NaN返回true，不是返回false
parserInt() 转成整数 parserFloat() 转成小数

			1.空字符串转成NaN    var str = '';
		 	2.忽略前后空格		var  str1 = '     10.3    ';
		 	3.忽略前边的0		var  str2 = '  000010.6  ';
		 	4.忽略第一位非数字后边	var str3 = '100px';
# 转布尔值
		 		Boolean()
		 		简单方法：！！
		 		1.字符串
		 			var str = '';  false
		 			var  str= '123' true
		 		2.数字
		 			var  a = 0 ;  false
		 			var  a1 = -2;  true
		 			var  Null = null  false
		 		3.undefined   false
		 		4.null   false
		 		5.Object  var a = {}  false
		 		var a2={q:1}  true

		 		false(5种): 	''  0  NaN  null undefined	
# 隐式类型转换
		 系统为了运算需要，偷偷的把数据类型转换
		  
		 我们主动调用某种方法，明确的将一种数据类型转成指定数据类型，叫显示类型转换
转换数字可以用 Number直接转 paserInt paserFloat

隐式类型转换
# 5-29
# 运算操作符
/ % ++ --
# 关系操作符
< > <= >= == === != !== (!== 两者不等) 返回布尔值成立true 不成立false

# 逻辑操作符
！取反 || 或 a || b 如果前边为真，返回前边，如果前边为假，返回后边 && 与 并且 a && b 如果前边为真，返回后边，如果前边为假，返回前边

# 赋值操作符
= += -= *= /= %=

# 逗号操作符
多个值间用逗号 逗号在赋值时，返回最后一个值

# 条件操作符，三目
		 	一元，二元，三元
		 	a?b:c
		 	a:判断条件
		 	如果判断条件为真，执行b，为假执行c
循环 * var i=0; while(i<10){ //执行代码 i++ } * for(var i=0;i<10;i++){ * //执行代码 * } * * for和while都是先判断条件，后执行
# do while
		先执行后判断条件
		至少执行一次时用这个
		var n = 0;
		do{
			console.log(n);
			n++;
		}while(n>10)
# switch
			1.if可以转成switch,但不是所有switch都可以转成if
		 	2.switch精准判断，数据类型也必须相等
		 	3.穿透性(break)
switch(n){ case 10: alert(1) break; } break,终止,跳出循环 终止break后续代码执行，同时跳出循环，后边的循环也不执行 continue 跳过本次循环 跳过本次循环后续代码执行，继续执行后续循环代码

# 操作符优先
		()  
		typeof ! ++ -- 一元运算符
		* / %
		+ -
		> < >= <=
		== != !== ===
		&&
		||
		?:
		=
		,
# 函数
		 		复用多行代码，先声明函数，在需要用的地方调用该函数，函数里的代码会逐行执行
		 		函数声明式
		 			function fn(){
		 					
		 			}
		 			可以先调用，后声明,js会在当前作用域代码执行前，优先解析函数声明式,函数声明式在声明就觉得了可访问的范围
		 		函数表达式
		 			var fn = function(){}
		 			var obj={
		 				a:function(){}
		 			}
		 			只能先声明，后调用，可访问的范围由变量在哪声明决定
# 5-30
函数参数 形参和实参 形参 在函数内部使用的变量，在函数声明时要定义形参，默认值是undefined,写在小括号内，多个值间用逗号分隔 实参 在函数调用时传入的值，一一对应赋值给形参，写在函数调用的小括号里，多个值间用逗号分隔 传参
结构相同，功能相同，用函数传参

# arguments
			在函数内部使用，传入实参的集合,一般用在不定参时,在函数传入实参时，会一一对应赋值给形参，还会把实参存在arguments里
		 	[0],length
		 	arguments.callee:存的是该函数体
# getComputedStyle(元素对象)
			getComputedStyle是一个可以获取当前元素所有最终使用的CSS属性值。返回的是一个CSS样式声明对象([object CSSStyleDeclaration])，只读。（getComputedStyle方法是不支持IE6·8的,IE有一个自带的属性，currentStyle）

			获取某个元素对象渲染到页面上，计算后的样式的对象,带单位
			getComputedStyle(元素对象).样式名
			获取复合样式,颜色,css3需要注意下
var box = document.getElementById('box'); console.log(getComputedStyle(box).transform)

# break ,continue ,return 的区别及作用？
break 跳出总上一层循环，不再执行循环(结束当前的循环体) continue 跳出本次循环，继续执行下次循环(结束正在执行的循环 进入下一个循环条件) return 程序返回，不再执行下面的代码(结束当前的方法 直接返回)

# 5-31
# 作用域
	全局作用域和局部作用域
	全局作用域写在函数外边的
	局部作用域写在函数的内部
a ,fn , 是全局变量，函数
var a = 11;
function fn(){
b,fn2是局部变量，局部函数
	var b = 12;
	function fn2(){

	}
}
# 全局作用域
	全局变量，全局函数，全局可以访问
# 局部作用域
	局部变量
	函数只能在该函数内部访问,外部访问不了
# 作用域链
	使用变量/函数时，查找规则
			 		
	函数内部->形参->函数外部
for in只能循环全部
for可以循环全部或者局部，可正可倒
div~p 兄弟哦 div 后面的所有P
div+p 兄弟哦 div后面紧挨着的第一个p
div p 父子 孙子 div内部的所有P
div>p  父子 div内部第一级所有p
# window
	是js里最外边的对象,当写window下的属性或方法时，可以忽略不写window
