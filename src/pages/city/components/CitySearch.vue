<template>
	<div>
		<div class="search-box">
			<input type="text" v-model="keyword" placeholder="输入城市名或拼音" class="search-input">
		</div>
		<div class="search-content" ref="search" v-show="this.keyword">
			<ul>
				<li class="search-item border-bottom" v-for="item in list" :key="item.id">{{item.name}}</li>
				<li class="search-item border-bottom" v-show="hasNoData">没有找到匹配的数据</li>
			</ul>
		</div>
	</div>
</template>

<script>
	import Bscroll from "better-scroll"
	export default {
		name: "CitySearch",
		props: {
			cities: Object
		},
		data: function () {
			return {
				keyword: "",
				list: [],
				timer: null
			}
		},
		computed: {
			hasNoData: function () {
				return !this.list.length
			}
		},
		watch: {
			keyword: function () {
				if (this.timer) {
					clearTimeout(this.timer);
				}
				if(!this.keyword){
					this.list = [];
					return
				}
				this.timer = setTimeout(() => {
					const result = [];
					for (let i in this.cities) {
						this.cities[i].forEach((value) => {
							if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
							result.push(value);
							}
						});
					}
					this.list = result;
				}, 100);
			}
		},
		mounted: function () {
			this.scroll = new Bscroll(this.$refs["search"]);
		}
	}
</script>

<style scoped lang="stylus">
	@import "~styles/varibles"
	.search-box
		background $bgColor
		height .70rem
		padding 0 .1rem
		.search-input
			box-sizing border-box
			width 100%
			height .5rem
			margin .1rem 0
			border-radius .1rem
			padding 0 .20rem
			color #666
			text-align center

	.search-content
		z-index 1
		overflow hidden
		position absolute
		left 0
		right 0
		bottom 0
		top 1.56rem
		background #eee
		.search-item
			height .66rem
			line-height .66rem
			padding-left .2rem
			color #666
			background #fff
</style>
