<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
	</div>
</template>

<script>
	import CityHeader from './components/cityHeader'
	import citySearch from './components/citySearch'
	export default {
        name: "City",
		components: {
        	CityHeader,
			citySearch
		}
    }
</script>

<style scoped>

</style>
