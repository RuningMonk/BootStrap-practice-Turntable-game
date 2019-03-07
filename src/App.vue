<template>
	<div id="app">
		<div class="modal fade" id="login-modal" tabindex="-1">
			<div class="modal-dialog">
				<div class="modal-content">
					<div class="modal-header">
						<button class="close" data-dismiss="modal">&times;</button>
						<h4>用户登录</h4>
					</div>
					<div class="modal-body">
						<button id="get" value="get">get</button>
						<button id="post" value="post">post</button>
					</div>
					<div class="modal-footer">
						<button class="btn btn-primary">登录</button>
					</div>
				</div>
			</div>
		</div>
		<nav class="navbar navbar-inverse navbar-fixed-top">
			<div class="container">
				<div class="navbar-header">
					<button class="navbar-toggle" data-toggle="collapse" data-target="#responsive-navbar">
						<span class="icon-bar"></span>
						<span class="icon-bar"></span>
						<span class="icon-bar"></span>
					</button>
					<a href="#" class="navbar-brand"><strong>BuZai</strong>.cnm</a>
				</div>
				<div class="collapse navbar-collapse" id="responsive-navbar">
					<ul class="nav navbar-nav">
						<li class="active"><a href="#">标签1</a></li>
						<li><a href="#">标签2</a></li>
						<li><a href="#">标签3</a></li>
					</ul>
					<form action="" class="navbar-form navbar-left">
						<input type="text" placeholder="搜索..." class="form-control">
						<button type="submit">
							<span class="glyphicon glyphicon-search"></span>
						</button>
					</form>
					<a href="" class="btn btn-primary btn-sm navbar-btn navbar-right hidden-xs">订阅课程</a>
					<div class="profile navbar-right">
						<ul class="nav navbar-nav">
							<li><a href="" data-toggle="modal" data-target="#login-modal">登录</a></li>
							<li><a href="">注册</a></li>
						</ul>
						<p class="navbar-text" v-show="false">你好,<a href="#" class="navbar-link">Tom</a></p>
					</div>
				</div>
			</div>
		</nav>
		<div class="alert alert-info container">
			<h1>提示</h1>
			<p>
				千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
				模态框的 HTML 代码放置的位置
				务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
				千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
				模态框的 HTML 代码放置的位置
				务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
				千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
				模态框的 HTML 代码放置的位置
				务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
			</p>
		</div>
		<div class="container">
			<div class="carousel slide" data-ride="carousel" id="slideshow">
				<ol class="carousel-indicators">
					<li data-target="#slideshow" data-slide-to="0" class="active"></li>
					<li data-target="#slideshow" data-slide-to="1"></li>
					<li data-target="#slideshow" data-slide-to="2"></li>
				</ol>
				<div class="carousel-inner">
					<div class="item active">
						<img src="holder.js/1200x500/auto?text=Bootstrap">
					</div>
					<div class="item">
						<img src="holder.js/1200x500/auto?text=JavaScript">
					</div>
					<div class="item">
						<img src="holder.js/1200x500/auto?text=Vue">
					</div>
				</div>
				<a href="#slideshow" data-slide="prev" class="left carousel-control">
					<span class="glyphicon glyphicon-chevron-left"></span>
				</a>
				<a href="#slideshow" data-slide="next" class="right carousel-control">
					<span class="glyphicon glyphicon-chevron-right"></span>
				</a>
			</div>
		</div>
		<div class="text-center control_div">
			<div class="btn-group">
				<button class="btn btn-default" id="prev-pic">
					<span class="glyphicon glyphicon-backward"></span>
				</button>
				<button class="btn btn-default" id="play">
					<span class="glyphicon glyphicon-play"></span>
				</button>
				<button class="btn btn-default" id="next-pic">
					<span class="glyphicon glyphicon-forward"></span>
				</button>
			</div>
		</div>
		<router-view />
	</div>
</template>

<script>
	export default {
		name: 'App',
		mounted() {
			$("#get").click(function() {
				$.ajax({
					url: 'http://localhost:2400/get',
					type: "GET",
					data: {
						name: 'get',
						type: 'get'
					},
					dataType: 'JSON',
					success: function(data) {
						console.log(data)
					},
					error: function(err) {
						console.log('失败')
					}
				})
			});
			$("#post").click(function() {
				$.ajax({
					url: 'http://localhost:2400/post',
					type: "POST",
					data: {
						name: 'post',
						type: 'post'
					},
					dataType: 'JSON',
					success: function(data) {
						console.log(data)
					},
					error: function(err) {
						console.log('失败')
					}
				})
			})

			$(function() {
				$("#prev-pic").click(function() {
					$('#slideshow').carousel('prev')
				})
				$("#next-pic").click(function() {
					$('#slideshow').carousel('next')
				})
			})
		}
	}
</script>

<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}

	.navbar-form {
		position: relative;
	}

	.navbar-form button[type="submit"] {
		position: absolute;
		top: 33%;
		right: 20px;
		background: none;
		border: none;
	}

	@media (min-width: 768px) {
		.navbar-inverse button[type="submit"] {
			top: 23%
		}
	}

	.navbar-form .glyphicon {
		color: #999999;
	}

	.control_div {
		margin-top: 10px;
	}
</style>
