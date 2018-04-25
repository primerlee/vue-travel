<template>
	<ul>
		<li class="item" v-for="key in letters" :key="key" :ref="key" @click="handleLetterClick"
			@touchstart.prevent="handleTouchStart"
			@touchmove="handleTouchMove" @touchend="handleTouchEnd">{{key}}
		</li>
	</ul>
</template>

<script>
	export default {
		name: "CityAlphabet",
		props: {
			cities: Object
		},
		data: function () {
			return {
				touchStatus: false,
				startY: 0,
				timer: null
			}
		},
		computed: {
			letters: function () {
				let letters = [];
				for (let i in this.cities) {
					letters.push(i);
				}
				return letters;
			}
		},
		updated: function (){
			this.startY = this.$refs["A"][0].offsetTop;
		},
		methods: {
			handleLetterClick: function (ev) {
				let element = ev.target.innerText;
				this.$emit("clicked", element);
			},
			handleTouchStart: function () {
				this.touchStatus = true;
			},
			handleTouchMove: function (e) {
				if (this.touchStatus) {
					if(this.timer){
						clearTimeout(this.timer);
					}
					this.timer = setTimeout(() => {
						const moveY = e.touches[0].clientY - 68;
						const index = Math.floor((moveY - this.startY) / 20);
						if(index >= 0 && index < this.letters.length ){
							this.$emit("clicked", this.letters[index]);
						}
					}, 10);

				}
			},
			handleTouchEnd: function () {
				this.touchStatus = false;
			}
		}
	}
</script>

<style scoped lang="stylus">
	@import "~styles/varibles.styl"
	ul
		position absolute
		right 0
		bottom 0
		top 1.56rem
		width .3rem
		display flex
		flex-direction column
		justify-content center
		li
			text-align center
			line-height .4rem
			color $bgColor
</style>
