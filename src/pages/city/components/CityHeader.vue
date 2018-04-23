<template>
	<div>
		<div class="city-header">城市选择
			<router-link to="/">
				<div class="iconfont icon-fanhui header-back"></div>
			</router-link>
		</div>
	</div>
</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style scoped lang="stylus">
	@import "~styles/varibles.styl"
	.city-header
		position relative
		height $headerHeight
		line-height $headerHeight
		text-align center
		background $bgColor
		font-size .32rem
		color #fff
		.header-back
			position absolute
			left 0
			top 0
			font-size .40rem
			width .80rem
			text-align center
			color #fff
</style>
