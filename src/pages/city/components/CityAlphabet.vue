<template>
    <ul>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
		<li class="item">A</li>
	</ul>
</template>

<script>
    export default {
        name: "CityAlphabet"
    }
</script>

<style scoped lang="stylus">
	@import "~styles/varibles.styl"
	ul
		position absolute
		right 0
		bottom 0
		top 1.56rem
		width .3rem
		display flex
		flex-direction column
		justify-content center
		li
			text-align center
			line-height .4rem
			color $bgColor
</style>
