<template>
	<view>user</view>
</template>

<script>
export default {
	data() {
		return {};
	},
	onLoad() {
		// uni.hideTabBar()
		uni.setTabBarBadge({
			index: 1,
			text: '2'
		});
		uni.showTabBarRedDot({
			index: 0
		});
	}
};
</script>

<style lang="less"></style>
