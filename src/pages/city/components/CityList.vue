<template>
    <div class="list">
		<div class="section">
			<div class="title">当前城市</div>
			<div class="city-list border-topbottom">
				<div class="city-wrap"><div class="city">北京</div></div>
			</div>
		</div>
		<div class="section">
			<div class="title">热门城市</div>
			<div class="city-list border-topbottom">
				<div class="city-wrap"><div class="city">北京</div></div>
				<div class="city-wrap"><div class="city">北京</div></div>
				<div class="city-wrap"><div class="city">北京</div></div>
				<div class="city-wrap"><div class="city">北京</div></div>
				<div class="city-wrap"><div class="city">北京</div></div>
				<div class="city-wrap"><div class="city">北京</div></div>
			</div>
		</div>
		<div class="section">
			<div class="title">A</div>
			<ul class="border-topbottom">
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
			</ul>
		</div>
		<div class="section">
			<div class="title">A</div>
			<ul class="border-topbottom">
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
			</ul>
		</div>
		<div class="section">
			<div class="title">A</div>
			<ul class="border-topbottom">
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
				<li class="border-bottom">杭州</li>
			</ul>
		</div>
	</div>
</template>

<script>
    export default {
        name: "CityList"
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
