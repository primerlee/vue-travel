<template>
	<div>
		<swiper :options="swiperOption" v-if="showIcons">
			<swiper-slide v-for="(page, index) in pages" :key="index">
				<div class="icons">
					<div class="icon" v-for="item in page" :key="item.id">
						<div class="icon-img">
							<img :src="item.imgUrl" alt="">
						</div>
						<p>{{item.desc}}</p>
					</div>
				</div>
			</swiper-slide>
			<div class="swiper-pagination" slot="pagination"></div>
		</swiper>
		<div class="location">
			<div class="left"><span class="iconfont icon-aui-icon-location"></span> 定位失败</div>
			<div class="right"><span class="iconfont icon-internet"></span> 五折泡温泉</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: 'HomeIcons',
		props: {
			list: Array
		},
		data: function(){
			return {
				swiperOption: {
					pagination: '.swiper-pagination',
					autoplay: false
				}
			}
		},
		computed: {
			pages() {
				const pages = [];
				this.list.forEach((item, index) => {
					const page = Math.floor(index / 8);
					if (!pages[page]) {
						pages[page] = [];
					}
					pages[page].push(item);
				});
				return pages
			},
			showIcons () {
				return this.list.length;
			}
		}
	}
</script>

<style lang="stylus" scoped>
	@import "~styles/varibles.styl"
	@import "~styles/mixins.styl"
	>>> .swiper-pagination-bullets
		bottom 0

	>>> .swiper-pagination-bullet-active
		background red
	.icons
		height: 0
		padding-bottom 55%
		overflow hidden
		.icon
			overflow hidden
			width 25%
			height 0
			float left
			padding-bottom 25%
			position relative
			.icon-img
				position absolute
				left 0
				top 0
				right 0
				bottom .44rem
				box-sizing border-box
				padding .1rem
				img
					height: 100%
					display block
					margin 0 auto
			p
				position absolute
				left 0
				right 0
				bottom 0
				height .44rem
				line-height .44rem
				color $darkColor
				text-align center
				ellipsis()

	.location
		width 100%
		height .88rem
		margin-top: .20rem
		display flex
		div
			width 50%
			line-height .88rem
			text-align center
			border-top 1px solid #ccc
			box-sizing border-box
			border-right 1px solid #ccc
			span
				font-size .32rem
		div.right
			border-right none
</style>
