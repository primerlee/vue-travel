<template>
	<div class="recommend">
		<div class="recommend-title">
			<span class="iconfont icon-like like-icon"></span>猜你喜欢
		</div>
		<ul>
			<router-link class="content border-bottom" tag="li" v-for="item in list" :key="item.id"
						 :to="'/detail/'+item.id">
				<div class="img-wrap">
					<img :src="item.imgUrl">
				</div>
				<div class="text">
					<p class="content-title">{{item.title}}</p>
					<p class="content-desc"><span>★★★★★</span>{{item.count}}条评论</p>
					<p class="price">¥ {{item.price}}<span>起</span><span class="address">{{item.address}}</span></p>
					<p class="add-info" v-show="item.desc">{{item.desc}}</p>
				</div>
			</router-link>
		</ul>
		<div class="more">查看所有产品</div>
	</div>
</template>
<script>
	export default {
		name: "HomeRecommend",
		props: {
			list: Array
		},
		data: function () {
			return {}
		}
	}
</script>
<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	.recommend
		margin-top .2rem
		.recommend-title
			line-height .8rem
			background #eee
			text-indent .2rem
			.like-icon
				color #f10
				padding-right .1rem
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
				padding-left .16rem
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
					span
						color #f10
						margin-right .20rem
				.price
					color #f10
					margin-top 0.2rem
					font-size .42rem
					span
						color $darkColor
						font-size .28rem
					.address
						float right
						margin-right .2rem
				.add-info
					height .34rem
					line-height .34rem
					margin .2rem 0
					color #f10
					font-size .26rem
		.more
			text-align center
			color #25a4bb
			font-size .32rem
			height 1rem
			line-height 1rem
</style>
