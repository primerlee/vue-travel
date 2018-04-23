<template>
    <div class="search-box">
		<input type="text" placeholder="输入城市名或拼音" class="search-input">
	</div>
</template>

<script>
    export default {
        name: "CitySearch"
    }
</script>

<style scoped lang="stylus">
	@import "~styles/varibles"
	.search-box
		background $bgColor
		height .70rem
		padding 0 .1rem
		.search-input
			box-sizing border-box
			width 100%
			height .5rem
			margin .1rem 0
			border-radius .1rem
			padding 0 .20rem
			color #666
			text-align center
</style>
