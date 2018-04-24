<template>
	<div>
    <div class="banner" @click="handleBannerClick">
		<img class="banner-img" src="//img1.qunarzz.com/wugc/p3/201206/02/44c1fe10b91aed6793835fbb.jpg_600x330_2ae2ceaa.jpg" alt="">
		<div class="banner-info">
			<div class="title">西溪国家湿地公园(AAAAA景区)</div>
			<div class="number"><span class="iconfont icon-like"> 9</span></div>
		</div>
		<div class="back-icon">
			<router-link to="/"><span class="iconfont icon-fanhui"></span></router-link>
		</div>
	</div>
		<common-gallery :images="images" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
	</div>
</template>

<script>
	import CommonGallery from 'common/Gallery'
    export default {
        name: "DetailBanner",
		components: {
        	CommonGallery
		},
		data: function () {
			return {
				images: ["http://img1.qunarzz.com/sight/p0/1611/be/be9fc1bcf93da153a3.img.jpg_r_800x800_52953aa5.jpg","http://img1.qunarzz.com/sight/p0/1511/fe/fe1e93a7d9b5d7ac90.img.jpg_r_800x800_8a546471.jpg"],
				showGallery: false
			}
		},
		methods: {
			handleBannerClick: function () {
				this.showGallery = true
			},
			handleGalleryClose: function () {
				this.showGallery = false
			}
		}
    }
</script>

<style scoped lang="stylus">
	>>>.router-link-active
		color #fff
	.banner
		position relative
		.banner-img
			width 100%
		.banner-info
			position absolute
			left 0
			bottom 0
			right 0
			height .66rem
			line-height .66rem
			color #fff
			display flex
			background linear-gradient(to bottom, rgba(0,0,0,.3), rgba(0,0,0,.8))
			.title
				flex 1
				padding-left .2rem
			.number
				height .4rem
				line-height .4rem
				margin-top .13rem
				padding 0 .2rem
				background rgba(0,0,0,9)
				border-radius .2rem
				margin-right .2rem
		.back-icon
			width .6rem
			height .6rem
			border-radius 50%
			color #fff
			background rgba(0,0,0,9)
			position absolute
			left .2rem
			top .2rem
			line-height .6rem
			text-align center
</style>
