## velocity.js ##

	$element.velocity({
		width: "500px",  
		property2: value2
	}, {
		/* Velocity's default options */
		duration: 400,
		easing: "swing",
		queue: "",
		begin: undefined,
		progress: undefined,
		complete: undefined,
		display: undefined,
		visibility: undefined,
		loop: false,
		delay: false,
		mobileHA: true
	});
***
#### 可选参数 
+ duration 持续时间
+ easinng 缓动函数
+ queue 动画队列，按队列顺序执行动画，使多个.velocity按顺序执行而非同时执行
+ begin 动画开始执行前函数
+ complete 执行完回调函数
+ progress 进度函数

> 0. function(elements, complete, remaining, start, tweenValue) {}
> 1. elements 运动对象	
> 2. complete (0,1) 表示当前进度
> 3. remaining 距完成动画还需的时间
> 4. start 开始的绝对时间 Unix时间戳
> 5. tween补间值类似于D3的.domain([-1, 0, 1]).range(["red", "white", "green"]);
> 6. domain相对于动画执行时间 tween相对于 range 输出值域

+ mobilHA 开启手机硬件加速 默认开启
+ loop false true number flase 不循环 true 循环执行 数字为循环次数
+ delay 延时执行
+ dispaly visiblity 在complete后执行

***
	
### 指令		
	$element
	    .velocity("fadeIn", { duration: 1500 }) //淡入
	    .velocity("fadeOut", { delay: 500, duration: 1500 })//淡出
	    .velocity("slideDown", { duration: 1500 })//下滑进入
	    .velocity("slideUp", { delay: 500, duration: 1500 })//向上收起
	    .velocity("scroll", { duration: 1500, easing: "spring" })//滑动缓动效果
	    .velocity("scroll", { container: $("#container") })//滑动到指定位置，想起fullpage的anchors
	    .velocity("scroll", { offset: "750px", mobileHA: false })//滚动到具体位置
	    .velocity("stop"),
	    .velocity("stop", "myQueue"); // Custom queue stop//停止一个队列中的动作
		.velocity("finish");//完成动画,配合setTimeout可提前完成
    	.velocity("reverse");//执行反向动画


 ***

 ##css3变换
	$element.velocity({
		translateZ: 0, // 移动端开启硬件加速
		translateX: "200px",
		rotateZ: "45deg"
	});


### color 

	$element.velocity({
	    backgroundColor: "#ff0000",//改变背景色
	    backgroundColorAlpha: 0.5,//改变背景色的透明度
	    colorRed: "50%",//RGB红色分量*0.5  (255,255,255)
	    colorBlue: "+=50",//RGB蓝色分量+50
	    colorAlpha: 0.85 //透明度为的0.85  0~1
	});
	

###Svg
	$svgRectangle.velocity({
		//svg css属性
	    x: 200,
	    r: 25,
	    translateX: "200px",
	    translateZ: "200px",
	    fill: "#ff0000",
	    stroke:"#000",只能支持16进制颜色
	    strokeRed: 255,//RGB颜色分量
	    strokeGreen: 0,
	    strokeBlue: 0,
	   //标准css属性
	    opacity: 1,
	    width: "50%"
	});

###属性

	opacity
	width (px, %)
	height (px, %)
	x (px, %)
	y (px, %)
	cx (px, %)
	cy (px, %)
	r (px, %)
	rx (px, %)
	ry (px, %)
	x1 (px, %)
	x2 (px, %)
	y1 (px, %)
	y2 (px, %)
	strokeDasharray (px)
	strokeDashoffset (px)
	strokeWidth (px)
	strokeMiterlimit (unitless)
	startOffset (%)
	translateX (px)
	translateY (px)
	scale (unitless)
	scaleX (unitless)
	scaleY (unitless)
	rotateZ (deg)
	skewX (deg)
	skewY (deg)
	rotateX (deg) (No IE)
	rotateY (deg) (No IE)
	translateZ (px, %) (No IE)
	transformPerspective (px only) (No IE)
	transformOriginX (px, %) (No IE)
	transformOriginY (px, %) (No IE)
	transformOriginZ (px, %) (No IE)
	fill (hex string)
	fillRed (unitless, %)
	fillGreen (unitless, %)
	fillBlue (unitless, %)
	fillAlpha (unitless, %)
	fillOpacity (unitless)
	stroke (hex string)
	strokeRed (unitless, %)
	strokeGreen (unitless, %)
	strokeBlue (unitless, %)
	strokeAlpha (unitless, %)
	strokeOpacity (unitless)
	stopColor (hex string)
	stopColorRed (unitless, %)
	stopColorGreen (unitless, %)
	stopColorBlue (unitless, %)
	stopColorAlpha (unitless, %)
	stopOpacity (unitless)
	offset (%)
	fontSize (px, %)
	letterSpacing (px, %)
	wordSpacing (px, %)

###hook

	//类似Jquery的css()方法
	//设置属性
	$.Velocity.hook($element, "translateX", "500px"); // Must provide unit type
	$.Velocity.hook(elementNode, "textShadowBlur", "10px"); // Must provide unit type
	//获取属性
	$.Velocity.hook($element, "translateX");
	$.Velocity.hook(elementNode, "textShadowBlur");


###未完待续...

	