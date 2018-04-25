<template>
	<div class="info border">
		<div class="wrap">
			<div class="left box border-right">
				<p class="title"><span>4.9</span>分 很棒</p>
				<p class="content">1234条评论 12条攻略</p>
			</div>
			<div class="right box">
				<p class="title">景点简介</p>
				<p class="content">开放时间、贴士</p>
			</div>
		</div>
		<div class="location border-top">
			<span class="iconfont icon-aui-icon-location"></span>
			浙江省杭州市西湖区之江路148号
		</div>
	</div>
</template>

<script>
    export default {
        name: "DetailInfo"
    }
</script>

<style scoped lang="stylus">
	.info
		border-radius .1rem
		padding .2rem
		.wrap
			display flex
			flex-direction row
			.box
				width 50%
				height .8rem
				text-align left
				padding-left .2rem
				margin-bottom .2rem
				font-size .30rem
				p
					line-height .44rem
				p.content
					color #999
					font-size .24rem
			.left
				.title
					color #f10
					span
						font-size .44rem
		.location
			font-size .28rem
			height .64rem
			line-height .64rem
</style>
