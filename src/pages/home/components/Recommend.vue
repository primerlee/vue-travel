<template>
	<div>
		<div class="recommend-title">
			猜你喜欢
		</div>
		<div class="content border-bottom" v-for="item in recommendList" :key="item.id">
			<div class="img-wrap">
				<img :src="item.imgUrl">
			</div>
			<div class="text">
				<p class="content-title">{{item.contentTitle}}</p>
				<p class="content-desc">{{item.contentDesc}}</p>
				<p class="price">价格 ¥ {{item.price}}<span>起</span><span class="address">{{item.address}}</span></p>
			</div>
		</div>
		<div class="more">查看所有产品</div>
	</div>
</template>
<script>
	export default {
		name: "HomeRecommend",
		data: function () {
			return {
				recommendList: [
					{
						id: "00001",
						imgUrl: "http://img1.qunarzz.com/wugc/p3/201206/02/44c1fe10b91aed6793835fbb.jpg_200x200_e7236f41.jpg",
						contentTitle: "西溪湿地",
						contentDesc: "浪漫西溪，邂逅美丽",
						price: "120",
						address: "西湖区"
					},
					{
						id: "00002",
						imgUrl: "http://img1.qunarzz.com/sight/p0/1412/be/c788f0f3767d2ea037b9b66d2010bfa4.water.jpg_200x200_ead93bcd.jpg",
						contentTitle: "宋城千古情",
						contentDesc: "浪漫西溪，邂逅美丽",
						price: "120",
						address: "西湖区"
					},
					{
						id: "00003",
						imgUrl: "http://img1.qunarzz.com/sight/p0/201408/14/771e7f0a85ca13b12c3fde0f7739440f.jpg_200x200_5e08c104.jpg",
						contentTitle: "杭州乐园",
						contentDesc: "浪漫西溪，邂逅美丽",
						price: "120",
						address: "萧山区"
					},
				]
			}
		}
	}
</script>
<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	.recommend-title
		margin-top .2rem
		line-height .8rem
		background #eee
		text-indent .2rem
	.content
		display flex
		.img-wrap
			width 1.8rem
			height 1.8rem
			padding .1rem
			img
				width 1.7rem
				height 1.7rem
		.text
			width 100%
			.content-title
				font-size .32rem
				height .44rem
				line-height .44rem
				margin-top: .26rem
				color $darkColor
			.content-desc
				font-size .26rem
				height .34rem
				line-height .34rem
				margin-top .2rem
			.price
				color #f10
				margin-top 0.2rem
				span
					color $darkColor
				.address
					float right
					margin-right .2rem
	.more
		text-align center
		color #25a4bb
		font-size .32rem
		height 1rem
		line-height 1rem
</style>
