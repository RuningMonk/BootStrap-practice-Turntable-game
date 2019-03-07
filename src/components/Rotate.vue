<template>
	<div id="Rotate" class="container">
		<div class="round">
			<canvas id="canvas"></canvas>
			<div class="start" @click="start()"></div>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				height: 0,
				num: 12,
				now: 0
			}
		},
		computed: {

		},
		methods: {
			start() {
				let canvas = document.getElementById("canvas");
				let prize = Math.ceil(Math.random() * this.num);
				let deg = Math.floor(prize * (360 / this.num) + 360 * 4); //产生旋转角度
				this.now += deg; //将产生的角度与现在的角度相加

				canvas.style.transform = "rotate(" + this.now + "deg)";
			},
			paint() {
				//生成抽奖轮盘
				let canvas = document.getElementById("canvas");
				canvas.width = 500;
				canvas.height = 500;
				let ctx = canvas.getContext('2d');
				let count = this.num; //设置块数
				let angle = Math.PI / 180 * (360 / count); //设置角度

				for (let i = 0; i < count; i++) {
					//设置当前块填充色
					if (i % 2 == 0) {
						ctx.fillStyle = '#ffb820';
					} else {
						ctx.fillStyle = '#ffcb3f';
					}
					//保存画布状态
					ctx.save();
					//将画布中心点(0,0)设置到(250,250)处
					ctx.translate(250, 250);
					//旋转画布
					ctx.rotate(-angle / 2); //旋转半个角度,让指针对准区域中间部分
					ctx.rotate(angle * i);
					//开始画线
					ctx.beginPath();
					//从初始点(画布的中心点(0,0)处)开始
					ctx.moveTo(0, 0);
					//以中心点为圆心画一个边长为240的圆弧,顺时针
					ctx.arc(0, 0, 240, 0, angle);
					//颜色填充
					ctx.fill();

					//写字
					ctx.fillStyle = "#000000";
					ctx.translate(Math.floor((Math.cos(angle / 2) * Math.cos(angle / 2) * 250)), Math.floor((Math.sin(angle / 2) *
						Math.cos(angle / 2) * 250)));
					ctx.rotate(angle / 2);
					ctx.font = "italic small-caps bold 16px arial";
					ctx.fillText(i + 1 + '等奖', -60, 0);


					//返回上次保存的画布状态(即起点为(0,0)处)
					ctx.restore();
				}
				// canvas.style.transform = "rotate("+(360/this.num)/2+"deg)"
			}
		},
		mounted() {

			this.paint();

		}
	}
</script>

<style scoped="scoped">
	#Rotate {
		width: 100%;
		height: auto;
		background-color: #F8F8F8;
	}

	.round {
		width: 50vw;
		height: 50vw;
		margin-left: auto;
		margin-right: auto;
		background-color: #006666;
		border-radius: 50%;
		position: relative;
		margin-bottom: 10vw;
	}

	#canvas {
		width: 100%;
		height: 100%;
		display: block;
		border-radius: 50%;
		transition: all 3s;
		margin-top: 10vw;
	}

	.start {
		width: 12%;
		height: 12%;
		border-radius: 370px;
		background-color: #F4EA2A;
		position: absolute;
		left: 44%;
		top: 44%;
		cursor: pointer;
		z-index: 10;
	}

	.start::after {
		content: "";
		display: block;
		position: absolute;
		border-left: 65px solid #f4ea2a;
		border-top: 2vw solid transparent;
		border-bottom: 2vw solid transparent;
		left: 5vw;
		top: 1vw;
	}
</style>
