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
***
	function(elements, complete, remaining, start, tweenValue) {
		//elements 运动对象
		//complete (0,1) 表示当前进度
		//remaining 距完成动画还需的时间
		//start 开始的绝对时间 Unix时间戳
		//tween补间值类似于D3的.domain([-1, 0, 1]).range(["red", "white", "green"]);
		//domain相对于动画执行时间 tween相对于 range 输出值域
	}
***
+ mobilHA 开启手机硬件加速 默认开启
+ loop false true number flase 不循环 true 循环执行 数字为循环次数