<template>
	<div class="wrapper">
		<div class="item" v-for="(item, index) in list" :key="index">
			<div class="item-title border-bottom"><span class="iconfont icon-hot" ></span>{{item.title}}</div>
			<div v-if="item.children" class="child-item">
				<detail-list :list="item.children"></detail-list>
			</div>
		</div>
	</div>
</template>

<script>
    export default {
        name: "DetailList",
		props: {
        	list: Array
		}
    }
</script>

<style scoped lang="stylus">
	.wrapper
		.item
			margin-top .2rem
			.item-title
				height .8rem
				line-height .8rem
				font-size .32rem
				span
					color #f10
					padding 0 .1rem
			.child-item
				padding 0 .4rem
				span
					display none
</style>
