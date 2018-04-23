<template>
	<swiper :options="swiperOption" v-if="showBanner">
		<swiper-slide v-for="item in list" :key="item.id">
			<img class="banner-img" :src="item.imgUrl" alt="">
		</swiper-slide>
		<div class="swiper-pagination" slot="pagination"></div>
	</swiper>
</template>
<script>
	export default {
		name: "HomeBanner",
		props: {
			list: Array
		},
		data: function () {
			return {
				swiperOption: {
					pagination: '.swiper-pagination',
					loop: true,
					autoplay: 3000
				}
			}
		},
		computed:  {
			showBanner: function () {
				return this.list.length
			}
		}
	}
</script>
<style lang="stylus" scoped>
	>>> .swiper-pagination-bullet-active
		background #fff
	.banner-img
		width 100%
</style>
