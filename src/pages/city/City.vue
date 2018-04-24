<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
		<city-list :city="hotCity" :cities="cities" :letter="letter"></city-list>
		<city-alphabet :cities="cities" @clicked="receiveLetter"></city-alphabet>
	</div>
</template>

<script>
	import axios from 'axios'
	import CityHeader from './components/CityHeader'
	import CitySearch from './components/CitySearch'
	import CityList from './components/CityList'
	import CityAlphabet from './components/CityAlphabet'

	export default {
        name: "City",
		components: {
        	CityHeader,
			CitySearch,
			CityList,
			CityAlphabet
		},
		data: function(){
        	return{
        		hotCity: [],
				cities: {},
				letter: ""
			}
		},
		methods: {
			getCityInfo: function () {
				axios.get("./api/city.json").then(this.getCityInfoSucc);
			},
			getCityInfoSucc: function (res) {
				var res = res.data;
				if(res.ret && res.data){
					this.hotCity = res.data.hotCities;
					this.cities = res.data.cities;
				}
			},
			receiveLetter: function (res) {
				this.letter = res;
			}
		},
		mounted: function () {
			this.getCityInfo()
		}
    }
</script>

<style scoped>

</style>
