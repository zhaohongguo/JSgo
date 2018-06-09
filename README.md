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

# 6-1
生命周期
	变量存在的周期，时间
			 		
	函数内声明的变量，在函数执行时创建，在函数执行完，如果没有引用，销毁
# 6-2

js自执行函数表达式
// 下面2个括弧()都会立即执行

(function () { /* code */ } ()); // 推荐使用这个
(function () { /* code */ })(); // 但是这个也是可以用的
和普通function执行的时候传参数一样，自执行的函数表达式也可以这么传参，因为闭包直接可以引用传入的这些参数，利用这些被lock住的传入参数，自执行函数表达式可以有效地保存状态。

// 这个代码是错误的，因为变量i从来就没背locked住
// 相反，当循环执行以后，我们在点击的时候i才获得数值
// 因为这个时候i操真正获得值
// 所以说无论点击那个连接，最终显示的都是I am link #10（如果有10个a元素的话）

var elems = document.getElementsByTagName('a');

for (var i = 0; i < elems.length; i++) {

    elems[i].addEventListener('click', function (e) {
        e.preventDefault();
        alert('I am link #' + i);
    }, 'false');

}

// 这个是可以用的，因为他在自执行函数表达式闭包内部
// i的值作为locked的索引存在，在循环执行结束以后，尽管最后i的值变成了a元素总数（例如10）
// 但闭包内部的lockedInIndex值是没有改变，因为他已经执行完毕了
// 所以当点击连接的时候，结果是正确的

var elems = document.getElementsByTagName('a');

for (var i = 0; i < elems.length; i++) {

    (function (lockedInIndex) {

        elems[i].addEventListener('click', function (e) {
            e.preventDefault();
            alert('I am link #' + lockedInIndex);
        }, 'false');

    })(i);

}

// 你也可以像下面这样应用，在处理函数那里使用自执行函数表达式
// 而不是在addEventListener外部
// 但是相对来说，上面的代码更具可读性

var elems = document.getElementsByTagName('a');

for (var i = 0; i < elems.length; i++) {

    elems[i].addEventListener('click', (function (lockedInIndex) {
        return function (e) {
            e.preventDefault();
            alert('I am link #' + lockedInIndex);
        };
    })(i), 'false');

}

# 闭包的理解
闭包就是一个函数引用另外一个函数的变量，因为变量被引用着所以不会被回收，因此可以用来封装一个私有变量。这是优点也是缺点，不必要的闭包只会徒增内存消耗！另外使用闭包也要注意变量的值是否符合你的要求，因为他就像一个静态私有变量一样。闭包通常会跟很多东西混搭起来，接触多了才能加深理解

# 6-3 之前总结
1.数据类型
				ECMA:string,number,boolean,null,undefined,object
				typeof:string,number,boolean,function,undefined,object
				
			2.数据类型转换
				String()， ''+数据类型 = 字符串类型
				Number()，
					string:''->0,纯数字字符串->数字
					boolean:true:1,false:0
					null:0
					空数组：0
					
					只用来字符串转数字，''->NaN
					parseInt()整数
					parseFloat()小数
					
				Boolean()，！！
				false:'',0,NaN,null,undefined
			3.NaN
				数字类型，其他数据类型转数字类型不成功的产物，NaN不等于任何值，包括自己，不可以做比较，都是false,isNaN()
			
			4.隐式类型转换
				var n = 'abc'-10 = NaN
			5.操作符，运算符
			运算：+ - * /
			关系：> < == ===
			逻辑：|| && ！
			逗号：
			条件，三目：a?b:c
			流程：
				switch,while
				switch(条件){
					case 条件1；
					break
				}
			条件 === 条件1，break穿透性
			
			break:跳出，终止循环
			continue:跳过本次循环
			
			6.运算符优先级
			
			7.函数参数，返回值
				形参，实参，arguments
			function fn(a){
				var a
			}
			
			return 数据类型，表达式
			1.终止函数内后续代码执行
			2.返回我们指定数据
			
			函数名() = 函数返回值
			就是return后边的东西
			function fn(){
				alert(1)
				return 2
			}
			alert(fn())
			
			
			function checkedAll(){
				if(全选了){
					return true;
				}else{
					return false
				}
			}
			
			if(checkedAll()){
				checkedAll()
			}else{
				checkedAll()
			}
			
			8.作用域
				全局，局部，作用域链
				
			9.预解析
			
			10.window
			
			11.闭包
			
			12.函数自执行
# 6-4
定时器
开启重复型定时器  setInterval（函数，时间间隔，实参....）
函数：每次执行的代码
时间间隔：单位毫秒，1秒=1000毫秒
实参：第3个参数往后，是传给函数的实参定时器返回值是数字类型的，从1开始往后排的编号，每次开启定时器都是新的编号，不管开启的是什么类型的定时器

关闭重复定时器：clearInterval(定时器编号)

var timer = setInterval(fn,1000);
var a = 1;
function fn(){
	a++;
	console.log(a)
	if(a==11){
		clearIntreval(tinmer)
	}
}
延时定时器
	延时多少毫秒执行一次
	开启延时定时器：setTimeout(函数,延时时间，实参..)
	函数：要执行的代码
	延迟时间：单位毫秒，1秒=1000毫秒
	实参：第3个参数往后，是传给函数的实参
	关闭延时型定时：clearTimeout（定时器编号）
this对象
	指针，指向该函数的执行环境
	全局环境下，window
	函数内部，this指向函数执行环境
形参和实参；就好比是洗衣机，形参就是洗衣机厂家给洗衣服人留的洗衣服口，实参就是洗衣服人在口中放入洗衣液和衣服。
###arguments 实参集合
>当我们不知道用户具体要传递几个值得时候（传递几个值都行）,此时我们无法设置形参的个数，遇到此类需求，需要使用函数内置的实参集合：argunments
1.argunments只有函数才有
2.不管执行函数的时候是否传递实参，argument一直存在，没有传递实参auguments是个空集合，传递了arguments中包含了所以传递的实参值。
3.不管是否设置了形参，arguments中始终存储所有实参信息
###arguments是一个类数组集合
1.以数字作为索引（属性名），从0开始
2.有一个length属性，存储的是当前几个长度（当前实参的个数）

argument.callee 当前函数的本身

# 6-5
# JS中的返回值 return
返回值是函数提供的一个出口：我们想在外面使用函数私有的信息，就需要通过return，把信息返回出来<br/>
return,后面跟着的都是值，如果函数中没有写return或者return后面啥也没有，默认返回的结果是undefined的，函数体中遇到return后，return后面的代码都不在执行了。
oBox.onclick = function(){
	把 一个没有名字的函数（有也可以）作为值赋值给一个变量或者一个元素的某个事件等  函数表达式
}
;(function(n){
	创建函数和执行函数在一起，创建完成立马执行   自执行函数
	n 形参
})(2);
# 自执行函数，符号只是控制语法规范
~function(n){}(10);
-function(n){}(10);
+function(n){}(10);
!funvtion(n){}(10);

var date = new Date()
时间对象，执行那一瞬间详细的时间信息
时间对象可以获取，也可以设置
直接获取，获取到的是本地时间
用后台传的时间设置，不要直接写，不然用户可以自己乱改
# 设置时间对象
	1.数字
		年，月，日，时，分，秒
	2.字符串
		月份：英文，首字母大小写都可以，月份全拼，简写也行
		时前面常用空格，逗号，-，/分隔
		月 日 年 时 分 秒 
	new 函数转成对象
	获取本地时间
	var date = new Date();
	设置时间
	月份从0开始，在设置月份时，实际月份-1
# 获取时间
	getFullYear()-年
	getMonth()-月，月份从0开始获取到的比时间月小1
	getDay()-星期几，周日是0
	getDate()-日
	getHours()-小时
	getSeconds()-秒
	getMilliseconds-毫秒
	getTime（）-当前时间到1970年1月1日0时0分0秒的毫秒差
# 设置时间
	如果设置的时间不符合实际情况，会自动往后换算然后设置时间
	setFullYear() - 年
	setMonth() - 月，设置时实际月份-1
	setDate() - 日
	setHours() - 小时
	setSeconds() - 秒
	setMilliseconds - 毫秒
	setTime() - 当前时间到1970年1月1日0时0分0秒的毫秒差
# 6-6
# 内置对象
## Array对象：

 属性：

 .length      获得数组的长度；

 方法：

 .concat（） 连接内容或者数组，组成新的数组；

 .join（n）  用n连接数组的每一项组成字符串，可以是空字符串；

 .pop（） 删除数组的最后一项数据，并返回删除的数据；

 .push（）  在数组最后加入新的内容返回新的数组的长度

 .reverse（） 翻转数组；

## String对象

 属性：

 .length  获取字符串的长度。

 方法：

 .charAt（n）  找到位置在n（索引）上的字符。

 .charCodeAt（n）  找到索引位置上的字符的编码：a=97，A=65。

 .indexOf（“m”） 查找字符m在字符串中第一次出现的索引；如果没有找到返回-1。

 .lastIndexOf（“m”）  查找字符m在字符串中最后一次出现的索引；如果没有找到返回-。

 .split（“n”）  以字符n分割字符串，并返回一个数组，空字符串时分割每个字符，如果字符串中没有该字符，同样返回数组。

 .substr（n，m）   截取字符串，从索引是n的位置开始截取，截取m个字符；如果只有一个参数n，那就是从n开始截取，截取到最后。

 .substring（n，m）  截取字符串，从索引是n的位置开始截取，截取到第m个字符（m娶不到）；如果只有一个参数n，那就是从n开始截取，截取到最后。

 .toLowerCase()   把字符串中的字母转化成小写。

 .toUpperCase()   把字符串中的字母转化成大写。

## Math对象

 方法：

 Math.pow(n,m)   n的m次方。

 Math.abs(n)    n到原点的距离（n的绝对值）。

 Math.round(n)   四舍五入取整。

 Math.floor(n)   地板函数（向下取整）。

 Math.ceil(n)    天花板函数 （向上取整）。

 Math.random()     返回0-1的随机数（取不到1）。

 注意：[n，m] 随机数为了能取到n，m                Math.floor(Math.random())*(m-n+1)+n)。

## 特殊字符

 \r  回车

 \n  换行

## Date对象  
 var date = new Date（）；

 方法：

 .toLocaleString()   以当前本地格式显示时间。

 date.getFullYear()   获取date对象的年份。

 date.getMonth()   获取月份（0-11）对应1-12月。

 date.getDate()   获取日期。

 date.getHours（） 获取小时。

 date.getMinutes（） 获取分钟

 date.getSeconds（） 获取多少秒

 date.getMilliSeconds（） 毫秒数

 date.getDay（）  获取星期几（0-6） 对应 周天至周六。

 date.getTime()   从1970年开始到时间日期的毫秒值（时间戳）

 date.setFullYear   设置年份

 ...
 
 ...

## 鼠标事件：

 onclick  鼠标点击事件

 onmouseover   鼠标放上

 onmouseout   鼠标离开

 ondblclick   双击事件

 onmousedown   鼠标按下

 onmouseup    鼠标抬起

 onmousemove    鼠标移动 

## 表单事件：

 onfocus  获得焦点

 onblur  失去焦点

 onsubmit   提交事件

 onchange  发生改变时候

 onreset  重置事件

## 键盘事件：

 onkeyup   按键抬起

 onkeydown     按键 按下

 onkeypress    键盘按下一次

## 窗口事件：

 onload  事件（页面加载完成后立即执行）

## 两种方法

 1、<script>window.onload=”init”；</script>   //init 为函数名

 2、<body onload=”init()”></body>   // init()  是一个完整的函数

## Event ：

 保存事件发生时的相关信息

 event.clientX:   事件发生时的X的坐标

 event.clientY:   事件发生时Y的坐标

 event.target     事件源

 注意：event必须通过以实参传递给函数才能使用

 

 Var obj=document.createElement(“标签名”);

 document.body.appendChild(obj); 

## Window对象

 alert（）

 confirm （）   弹窗显示 确定  取消

 prompt （）    输入框

 window .open(“链接”，“name”，“设置”);

 1、width

 2、height

 3、left

 4、top

 5、scrollbars    yes  no  滚动条

 6、toolbar   yes no 工具栏

 7、location    地址栏（浏览器）   

 8、close（）   只有通过js代码打开的窗口才能关闭

 每个个设置属性用“，”隔开，7和8需要用户允许

## 定时器：

 一次性定时器：

 Var name1=window.setTimeout(“js代码”，时间t)

 执行： 时间t之后执行js代码 。

 周期：毫秒计算。
 
 反复性定时器：

 Var name2=window.setInterval(“js代码”，时间t)

 执行：每时间t就执行一次

 周期以毫秒计算

 清除定时器：必须给定时器一个名字

 一次性定时器  windowclearTimeout(name1);

 反复性定时器  window.clearInterval(name2);

# 6-7
 JS中常用的截取函数有3个：slice();substring();
 substr();他们都是0开头。
## slice();
 使用一个参数（n）里面是数字几就从几开始，有点也返回知道最后一位。
 使用两个参数(3,5)则表示的是从第3位截取到第5位之间
 如果只有一个参数并且这个参数为0，则返回整个参数。
 alert(a.slice(0,1))返回当前参数第一位。slice和substring的用法相同。如果有负数的出现他俩则不同。
 alert(a.slice(2,-5))  (2,3)
 alert(a.substring(2,-5)) 负5加上字符串长度8转换成正3(若第一位数字等于或大于第二位数字,则返回空字符串);
 split()用指定字符分隔字符串，把结果放到数组里返回
# Math,数学对象
 有数学方法供我们使用
	Math.PI	圆周率
	Math.abs()绝对值
	Math.cos()余弦
	Math.sin()正弦
	Math.tan()正切
	Math.ceil()向上取整
	Math.floor()向下取整
	Math.random()0~1之间的随机小数，不包含0和1
	Math.round()四舍五入
	Math.pow(a,b)a的b次方
	Math.sqrt(a,b)a开b次方
	Math.max(n1,n2...)最大值
	Math.min(n1,n2...)最小值
# JSON
	JavaScript Object Notation
	数据交换格式
	长得像对象的字符串
	两种规格'{}','[]'
	属性名必须是双引号
	不能写undefined
			 		
	字符串必须双引号、数字,布尔值，null,对象
			 		
			 		
			 		
	JSON.parse()
	JSON字符串转对象
	JSON.stringify()
	对象转JSON字符串

# 6-8
## array 数组
	存储0个或多个数据，有序性，多个数据间用逗号分隔
	创建数组方式	
		1.字面量
			var arr = [];
		2.对象
			var arr = new Array(数据1,数据2...)
			 如果括号里只有一个数据，并且是数字，代表设置数组的长度,而不是放入一个数字类型的数据
		3.Array.of(),ES6
			 为了解决方法2只有一个数据，并且是数字代表设置数组长度，ES6添加了一个方法Array.of()，传入一个数字，就是把数字放到数组内，而不是设置长度了
## array.push(数据1,数据2...)
			 作用：
			 	向数组的最后添加数据
			 参数：
			 	添加的数据，多个数据间用逗号分隔
			 	返回值：number
			 		新数组的长度（多少个数据）
array.pop()
			 作用：
			  	删除数组最后一个数据
			 返回值：混合
			  	  删除的那一个数据
array.shift()
			 作用：
			  	删除数组第一位数据
			 返回值：混合
		   	    返回删除的那一个数据 
array.unshift(数据1,数据2...)
			 作用：
			 	向数组的头部添加数据
			 参数：
			 	添加的数据，多个数据之间用逗号分隔
			 	返回值：number
			 		新数组的长度
array.lastIndexOf(target,[start])
			 	作用：
			 		从指定位置开始查找数组里是否有指定值
			 	参数：
			 		target：要找的值
			 		[start]:可选，起始位置，默认是最后一位
			 	返回值：number
			 		1.找到返回位置下标
			 		2.没找到返回-1
			 		3.从右向左
array.includes(target)
			  作用：
			 		数组里是否包含指定值
			  参数：
			  	target:指定值
			  返回值：boolean
			  		1.有,true
			       2.没有,false
			       3.===
array.slice(start,[end])
			 	作用：
			 		截取数组中的一段数据放新数组里返回
			 	参数：
			 		start：起始位置
			 		[end]:终止位置，可选，默认到最后一位
			 	返回值：array
			 	   1.不传参数，返回完整新数组
			 	   2.截取起始位置到终止位置的数据，不包含终止位置，放新数组里返回
			 	   3.负数，长度+负数
# 6-9
array.splice(pos,length,val1,val2...)
			 	作用：
			 		添加，删除，替换
			 	参数：
			 		pos:位置
			 		length:删除长度
			 		val1,val2:添加数据，多个用逗号分隔
			 	返回值：array
			 		1.如果有删除，把删除项放到数组里返回
			 		2.没删除，返回空数组
			 		3.操作的是原数组
	array.concat(val1,val2...)
			 作用： 		原数组和传入值放新数组里返回，连接2个数组
			  参数：
			 	val1,val2:添加的数据，多个之间用逗号
			  返回值：array
			 		1.原数组和新传入的值放到新数组里返回
			        2.不改变原数组
			        3.如果传入的是数组，会把原数组每项和传入数组的每项放到新数组里返回