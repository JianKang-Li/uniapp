<template>
	<view>demo</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	onReady() {
		// 建议不在onLoad中使用
		// uni.setNavigationBarColor({
		// 	//注意必要属性，文字颜色只能六位且只有黑白
		// 	backgroundColor: '#c00',
		// 	frontColor: '#ffffff'
		// });
		// uni.setNavigationBarTitle({
		// 	title: 'js控制标题'
		// });
	},
	onLoad() {
		uni.showNavigationBarLoading();
		setTimeout(() => {
			uni.hideNavigationBarLoading();
		}, 1000);
	}
};
</script>

<style lang="less"></style>
