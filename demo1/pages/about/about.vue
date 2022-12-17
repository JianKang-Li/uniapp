<template>
	<view>
		<pubTitle title="about" subtitle="about副标题" @click.native='onClick'></pubTitle>
		<view>about</view>
		<text>---------------</text>
		<myEvent title="组件间的传值" @myenv="showMsg" @click.native='onClick'></myEvent>
		<button type="primary" size="mini" @click="isShow=true">开启</button>
		<!-- <mypop :show="isShow" @close='closed'></mypop> -->
		<!-- <mypop :show="isShow" @update:show='show'></mypop> -->
		<mypop :show.sync="isShow"></mypop>
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
			showMsg(arg) {
				console.log(arg)
			},
			onClick() {
				console.log('click')
			},
			// closed() {
			// 	this.isShow = false
			// }
			// show(e) {
			// 	this.isShow = e
			// }
		},
		// created() {
		// 	console.log('about页面created')
		// },
		// mounted() {
		// 	console.log('about页面mounted')
		// }
	}
</script>

<style lang="less">

</style>
