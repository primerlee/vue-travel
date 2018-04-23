<template>
	<div class="border-top">
		<p class="notice"><span>票面价</span>是指通过景区指定窗口售卖的纸质门票上标注的价格</p>
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
		height .8rem
		line-height .8rem
		text-align center
		color $darkColor
		span
			font-size .30rem
			font-weight bold
</style>
