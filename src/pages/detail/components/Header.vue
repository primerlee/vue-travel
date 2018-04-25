<template>
	<div class="header">
		<div class="back-abs" v-show="backIconShow">
			<router-link to="/"><span class="iconfont icon-fanhui"></span></router-link>
		</div>
		<div class="back-fixed" v-show="!backIconShow" :style="opacityStyle">
			{{sightName}}
			<router-link to="/"><div class="iconfont icon-fanhui header-back"></div>
			</router-link>
		</div>
	</div>
</template>

<script>
    export default {
        name: "DetailHeader",
		data: function () {
			return {
				backIconShow: true,
				opacityStyle: {
					opacity: 0
				}
			}
		},
		props: {
			sightName: String
		},
		methods: {
        	handleScroll: function () {
        		console.log("scroll");
        		const top = document.documentElement.scrollTop;
        		if (top > 60){
        			let opacity = top / 180;
        			opacity = opacity > 1 ? 1: opacity;
        			this.opacityStyle = {
        				opacity
					};
        			this.backIconShow = false;
				}else{
					this.backIconShow = true;

				}
        		console.log()
			}
		},
		activated: function () {
			window.addEventListener("scroll", this.handleScroll, false);
		},
		deactivated: function () {
			window.removeEventListener("scroll", this.handleScroll, false);
		}
    }
</script>

<style scoped lang="stylus">
	@import "~styles/varibles.styl"
	>>> .router-link-active
		color #fff
	.header
		.back-abs
			width .6rem
			height .6rem
			border-radius 50%
			color #fff
			background rgba(0,0,0,9)
			position absolute
			left .4rem
			top .4rem
			line-height .6rem
			text-align center
		.back-fixed
			position fixed
			top 0
			left 0
			right 0
			width 100%
			height $headerHeight
			line-height $headerHeight
			text-align center
			background $bgColor
			font-size .32rem
			color #fff
			.header-back
				position absolute
				left 0
				top 0
				font-size .40rem
				width .80rem
				text-align center
				color #fff
</style>
