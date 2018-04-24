<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="section">
				<div class="title">当前城市</div>
				<div class="city-list border-topbottom">
					<div class="city-wrap">
						<div class="city">北京</div>
					</div>
				</div>
			</div>
			<div class="section">
				<div class="title">热门城市</div>
				<div class="city-list border-topbottom">
					<div class="city-wrap" v-for="item in city" :key="item.id">
						<div class="city">{{item.name}}</div>
					</div>
				</div>
			</div>
			<div class="section" v-for="(item, key) in cities" :key="key" :ref="key">
				<div class="title">{{key}}</div>
				<ul class="border-topbottom">
					<li class="border-bottom" v-for="innnerItem in item" :key="innnerItem.id">{{innnerItem.name}}</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
	import BScroll from 'better-scroll'

	export default {
		name: "CityList",
		props: {
			city: Array,
			cities: Object,
			letter: String
		},
		mounted: function () {
			this.scroll = new BScroll(this.$refs.wrapper);
		},
		watch: {
			letter: function () {
				if(this.letter){
					var ele = this.$refs[this.letter][0];
					this.scroll.scrollToElement(ele);
				}
			}
		}
	}
</script>

<style scoped lang="stylus">
	.border-topbottom
		&:before
			border-color #ccc
		&:after
			border-color #ccc

	.border-bottom
		&:before
			border-color #ccc

	.list
		position absolute
		left 0
		top 1.56rem
		right 0
		bottom 0
		overflow hidden
		.title
			height .50rem
			line-height .50rem
			background #eee
			color #666
			padding-left .1rem
		.city-list
			padding .1rem .3rem .1rem .1rem
			overflow hidden
			.city-wrap
				float left
				width 33.3%
				.city
					text-align center
					border 1px solid #ccc
					padding .1rem 0
					box-sizing border-box
					margin .1rem
					border-radius .06rem
		ul
			li
				padding-left .1rem
				height .6rem
				line-height .6rem

</style>
