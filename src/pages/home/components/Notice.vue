<template>
	<div>
		<p class="notice"><span class="iconfont icon-internet icon-alert"></span><span class="bold">票面价</span>是指通过景区指定窗口售卖的纸质门票上标注的价格</p>
	</div>
</template>
<script>
	export default {
		name: "HomeNotice"
	}
</script>
<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	.notice
		height .6rem
		line-height .6rem
		text-align center
		color $darkColor
		border-top 4px solid #eee
		font-size .24rem
		.icon-alert
			font-size .24rem
			padding-right .10rem
		.bold
			font-size .26rem
			font-weight bold
</style>
