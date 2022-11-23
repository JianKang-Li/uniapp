<template>
	<view>
		<view class="item">
			myItem自定义组件
		</view>
	</view>
</template>

<script>
	export default {
		name: "myitem",
		data() {
			return {

			};
		}
	}
</script>

<style lang="less">
	.item {
		width: 200rpx;
		height: 200rpx;
		background: orange;
		color: #ffffff;
		border-radius: 20rpx;
	}
</style>
