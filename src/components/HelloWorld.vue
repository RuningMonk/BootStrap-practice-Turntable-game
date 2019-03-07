<template>
	<div class="hello">
		<h1>{{ msg }}</h1>
		<div class="container">
			<div class="row">
				<div class="div1 col-md-8 col-lg-9">
					<h1>title1</h1>
					<p>不支持同时打开多个模态框
						千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
						模态框的 HTML 代码放置的位置
						务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
					</p>
					<div class="row">
						<div class="col-md-4">
							<h2>区域1</h2>
							<p>不支持同时打开多个模态框
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
							</p>
						</div>
						<div class="col-md-4">
							<h2>区域2</h2>
							<p>不支持同时打开多个模态框
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
							</p>
						</div>
						<div class="col-md-4">
							<h2>区域3</h2>
							<p>不支持同时打开多个模态框
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
							</p>
						</div>
						<div class="clearfix"></div>
						<div class="col-md-8">
							<h2>区域4</h2>
							<p>不支持同时打开多个模态框
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
							</p>
						</div>
						<div class="col-md-4">
							<h2>区域5</h2>
							<p>不支持同时打开多个模态框
								千万不要在一个模态框上重叠另一个模态框。要想同时支持多个模态框，需要自己写额外的代码来实现。
								模态框的 HTML 代码放置的位置
								务必将模态框的 HTML 代码放在文档的最高层级内（也就是说，尽量作为 body 标签的直接子元素），以避免其他组件影响模态框的展现和/或功能。
							</p>
						</div>
					</div>
				</div>
				<div class="div2 col-md-3 col-lg-2 col-md-offset-1 col-lg-offset-1 visible-lg visible-md">
					<h1>边栏</h1>
					<p>对于移动设备的附加说明
						这里提供了在移动设备上使用模态框有一些附加说明。请参考浏览器支持章节。
						Due to how HTML5 defines its semantics, the autofocus HTML attribute has no effect in Bootstrap modals. To
						achieve the same effect, use some custom JavaScript:
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'HelloWorld',
		data() {
			return {
				msg: 'Welcome to Your Vue.js App'
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	h1,
	h2 {
		font-weight: normal;
	}

	ul {
		list-style-type: none;
		padding: 0;
	}

	li {
		display: inline-block;
		margin: 0 10px;
	}

	a {
		color: #42b983;
	}

	.div1 {
		background-color: #FFDDDD;
	}

	.div2 {
		background-color: #EEEEEE;
	}
	
</style>
