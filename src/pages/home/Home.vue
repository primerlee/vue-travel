<template>
	<div class="container">
		<home-header :city="city"></home-header>
		<home-banner :list="bannerList"></home-banner>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>
		<home-notice></home-notice>
		<home-footer></home-footer>
	</div>
</template>

<script>
	import HomeHeader from './components/Header'
	import HomeBanner from './components/Banner'
	import HomeIcons from './components/Icons'
	import HomeRecommend from './components/Recommend'
	import HomeWeekend from './components/Weekend'
	import HomeNotice from './components/Notice'
	import HomeFooter from './components/Footer'
	import axios from 'axios'

	export default {
		name: "Home",
		components: {
			HomeHeader,
			HomeBanner,
			HomeIcons,
			HomeRecommend,
			HomeWeekend,
			HomeNotice,
			HomeFooter
		},
		data: function(){
			return {
				city: "",
				bannerList: [],
				iconList: [],
				recommendList: [],
				weekendList: []
			}
		},
		methods: {
			getHomeInfo: function () {
				axios.get("/api/index.json").then(
					this.getHomeInfoSuc
				)
			},
			getHomeInfoSuc: function (res) {
				var res = res.data;
				if(res.ret && res.data){
					this.city = res.data.city;
					this.bannerList = res.data.BannerList;
					this.iconList = res.data.iconList;
					this.recommendList = res.data.recommendList;
					this.weekendList = res.data.weekendList;
				}
			}
		},
		mounted: function () {
			this.getHomeInfo();
		}
	}
</script>

<style lang="stylus" scoped>

</style>
