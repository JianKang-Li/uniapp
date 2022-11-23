<template>
	<view>
		<pubTitle title="about" subtitle="about副标题" @click.native='onClick'></pubTitle>
		<view>about</view>
		<text>---------------</text>
		<myEvent title="组件间的传值" @myenv="show"></myEvent>
		<button type="primary" size="mini" @click="isShow=true">开启</button>
		<mypop :show="isShow" @close='closed'></mypop>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isShow: false
			};
		},
		methods: {
			show(arg) {
				console.log(arg)
			},
			onClick() {
				console.log('click')
			},
			closed() {
				this.isShow = false
			}
		}
	}
</script>

<style lang="less">

</style>
