<template>
	<div>
		<detail-banner :sightName="sightName" :bannerImg="bannerImg" :galleryImgs="galleryImgs"></detail-banner>
		<detail-header :sightName="sightName"></detail-header>
		<detail-list :list="list"></detail-list>
		<detail-footer></detail-footer>
	</div>
</template>

<script>
	import DetailBanner from './components/Banner'
	import DetailHeader from './components/Header'
	import DetailList from './components/List'
	import DetailFooter from 'common/footer/Footer'
	import axios from 'axios'

	export default {
		name: "Detail",
		components: {
			DetailBanner,
			DetailHeader,
			DetailList,
			DetailFooter
		},
		data: function () {
			return {
				sightName: "",
				bannerImg: "",
				galleryImgs: [],
				list: []
			}
		},
		methods: {
			getDetailInfo: function () {
				axios.get("./api/detail.json").then(this.getDetailInfoSucc);
			},
			getDetailInfoSucc: function (res) {
				var res = res.data;
				if(res.ret && res.data){
					this.sightName = res.data.sightName;
					this.bannerImg = res.data.bannerImg;
					this.galleryImgs = res.data.galleryImgs;
					this.list = res.data.categoryList
				}
			}
		},
		mounted: function () {
			this.getDetailInfo()
		}

	}
</script>

<style scoped lang="stylus">

</style>
