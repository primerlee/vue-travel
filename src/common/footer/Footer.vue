<template>
	<div class="footer">
		<ul class="ticket">
			<li><span class="iconfont icon-feiji800"></span><i>机票</i></li>
			<li><span class="iconfont icon-icon-"></span><i>酒店</i></li>
			<li><span class="iconfont icon-kezhangongyu"></span><i>公寓</i></li>
			<li><span class="iconfont icon-arrowdown"></span><i>更多</i></li>
		</ul>
		<ul class="about">
			<li><a href="#">登录</a></li>
			<li><a href="#">我的订单</a></li>
			<li><a href="#">最近浏览</a></li>
			<li><a href="#">关于我们</a></li>
		</ul>
		<div class="version">
			<div class="mobile">触屏版</div>
			<div class="pc">电脑版</div>
		</div>
		<p class="copy-right">Qunar 京ICP备05021087 <a href="#">意见反馈</a></p>
	</div>
</template>

<script>
    export default {
        name: "HomeFooter"
    }
</script>

<style lang="stylus" scoped>
	.footer
		background #eee
		ul
			overflow hidden
			text-align center
			height 1rem
			line-height 1rem
			li
				float: left
				width 25%
				color #9e9e9e

		ul.ticket
			font-size .24rem
			span
				font-size .40rem
				vertical-align middle
				margin-right .1rem
				text-decoration none

			i
				display inline-block
				line-height: 1.4
				border-bottom 1px solid #9e9e9e

		ul.about
			width 80%
		.version
			display flex
			height .8rem
			line-height .8rem
			border-top 1px solid #ddd
			padding 0 1rem;
			div
				text-align center
				width 50%
				font-size .32rem
			div.pc
				color #25a4bb
		.copy-right
			text-align center
			height .6rem
			line-height .6rem
			padding-bottom .2rem
</style>
