<template>
    <transition>
		<slot></slot>
	</transition>
</template>

<script>
    export default {
        name: "fadeAnimation"
    }
</script>

<style scoped lang="stylus">
	.v-enter, .v-leave-to
		opacity 0
	.v-enter-active, .v-leave-active
		transition all 1s
</style>
