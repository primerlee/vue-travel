<template>
	<div class="container" @click="handleGalleryClick">
		<div class="wrapper">
			<swiper :options="swiperOption">
				<swiper-slide v-for="(item, index) in images" :key="index">
					<img class="banner-img" :src="item" alt="">
				</swiper-slide>
				<div class="swiper-pagination" slot="pagination"></div>
			</swiper>
		</div>
	</div>
</template>

<script>
    export default {
        name: "CommonGallery",
		data: function () {
			return {
				swiperOption: {
					pagination: ".swiper-pagination",
					paginationType: "fraction",
					observer: true,
					observeParents: true
				}
			}
		},
		props: {
        	images: {
        		type: Array,
				default: function () {
					return  []
				}
			}
		},
		methods: {
			handleGalleryClick: function () {
				this.$emit("close")
			}
		}
    }
</script>

<style scoped lang="stylus">
	.container >>> .swiper-container
		overflow inherit
	.container
		z-index 999
		display flex
		flex-direction column
		justify-content center
		position fixed
		left: 0
		top: 0
		right 0
		bottom 0
		background #000
		.wrapper
			width 100%
			height 0
			padding-bottom 100%
			.swiper-pagination
				color #fff
				bottom -2rem
			.banner-img
				width 100%

</style>
