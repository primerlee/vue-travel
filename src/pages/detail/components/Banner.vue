<template>
	<div>
    <div class="banner" @click="handleBannerClick">
		<img class="banner-img" :src="bannerImg" alt="">
		<div class="banner-info">
			<div class="title">{{sightName}}</div>
			<div class="number"><span class="iconfont icon-like">{{galleryImgs.length}}</span></div>
		</div>
	</div>
		<fade-animation>
			<common-gallery :images="galleryImgs" v-show="showGallery" @close="handleGalleryClose"></common-gallery>
		</fade-animation>
	</div>
</template>

<script>
	import CommonGallery from 'common/gallery/Gallery'
	import fadeAnimation from 'common/fade/fadeAnimation'
    export default {
        name: "DetailBanner",
		components: {
        	CommonGallery,
			fadeAnimation
		},
		props: {
			sightName: String,
			bannerImg: String,
			galleryImgs: Array,
			list: Array
		},
		data: function () {
			return {
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
</style>
