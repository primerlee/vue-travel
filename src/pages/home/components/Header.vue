<template>
	<div class="header">
		<div class="header-left"><div class="iconfont icon-fanhui back-icon"></div></div>
		<div class="header-input"><span class="iconfont icon-sousuo"></span>输入城市景点游玩主题</div>
		<div class="header-right">{{this.city}}<span class="iconfont icon-arrowdown arrow-down"></span></div>
	</div>
</template>

<script>
	export default {
		name: "HomeHeader",
		props: {
			city: String
		}
	}
</script>

<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	.header
		display flex
		height .86rem
		line-height .86rem
		background $bgColor
		color #fff
		.header-left
			width .64rem
			float left
			.back-icon
				text-align center
				font-size .4rem
		.header-input
			flex 1
			height .64rem
			background #fff
			border-radius .1rem
			margin-top .12rem
			margin-left .2rem
			color #ccc
			line-height .64rem
			padding-left .18rem
		.header-right
			width 1.24rem
			float right
			text-align center
			.arrow-down
				font-size .24rem
</style>
