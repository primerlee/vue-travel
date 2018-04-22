<template>
	<swiper :options="swiperOption">
		<!-- slides -->
		<swiper-slide v-for="item in bannerList" :key="item.id">
			<img class="banner-img" :src="item.imgUrl" alt="">
		</swiper-slide>
		<!-- Optional controls -->
		<div class="swiper-pagination" slot="pagination"></div>
	</swiper>
</template>
<script>
	export default {
		name: "HomeBanner",
		data: function () {
			return {
				swiperOption: {
					pagination: '.swiper-pagination',
					loop: true
				},
				bannerList: [
					{
						id: '00001',
						imgUrl: 'http://img1.qunarzz.com/piao/fusion/1609/69/e232563244dbc302.jpg_640x200_5d31908b.jpg'
					},
					{
						id: '00002',
						imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/fd/e2ef81eb09dd8a02.jpg_640x200_8d784252.jpg'
					}
				]
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
