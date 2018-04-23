<template>
	<div>
		<div class="recommend-title">
			周末去哪
		</div>
		<div class="content border-bottom" v-for="item in list" :key="item.id">
			<img :src="item.imgUrl">
			<div class="text">
				<p class="content-title">{{item.title}}</p>
				<p class="content-desc">{{item.desc}}</p>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: "HomeWeekend",
		props: {
			list: Array
		}
	}
</script>
<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	.recommend-title
		line-height .8rem
		background #eee
		text-indent .2rem
	.content
		width 100%
		img
			width 100%
		.text
			width 100%
			padding 0 .2rem
			.content-title
				font-size .32rem
				height .40rem
				line-height .40rem
				margin-top: .2rem
				color $darkColor
			.content-desc
				font-size .26rem
				height .4rem
				line-height .4rem
				margin .15rem 0

</style>
