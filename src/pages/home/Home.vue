<template>
	<div class="container">
		<home-header></home-header>
		<home-banner></home-banner>
		<home-icons></home-icons>
		<home-recommend></home-recommend>
		<home-weekend></home-weekend>
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
		}
	}
</script>

<style lang="stylus" scoped>

</style>
