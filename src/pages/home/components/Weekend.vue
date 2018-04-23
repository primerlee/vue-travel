<template>
	<div>
		<div class="recommend-title">
			周末去哪
		</div>
		<div class="content border-bottom" v-for="item in recommendList" :key="item.id">
			<img :src="item.imgUrl">
			<div class="text">
				<p class="content-title">{{item.contentTitle}}</p>
				<p class="content-desc">{{item.contentDesc}}</p>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: "HomeWeekend",
		data: function () {
			return {
				recommendList: [
					{
						id: "00001",
						imgUrl: "http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg",
						contentTitle: "西湖十景",
						contentDesc: "浪漫西溪，邂逅美丽",
					},
					{
						id: "00002",
						imgUrl: "http://img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg",
						contentTitle: "宋城千古情",
						contentDesc: "浪漫西溪，邂逅美丽",
					},
					{
						id: "00003",
						imgUrl: "http://img1.qunarzz.com/sight/source/1505/bc/83feb2e003d0dd.jpg_r_640x214_0b7269b8.jpg",
						contentTitle: "杭州多样乐园",
						contentDesc: "浪漫西溪，邂逅美丽",
					}
				]
			}
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
				margin-top: .1rem
				color $darkColor
			.content-desc
				font-size .26rem
				height .4rem
				line-height .4rem
				margin .15rem 0

</style>
