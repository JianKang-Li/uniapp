<template>
	<view class="content">
		<button type="primary" @click="showSuccess">showSuccess</button>
		<button type="warn" @click="showError">showError</button>
		<view class=""><navigator url="/pages/demo/demo">跳转到demo页面</navigator></view>
		<view class=""><button @click="showModal">showModal</button></view>
	</view>
</template>

<script>
export default {
	methods: {
		showSuccess() {
			uni.showToast({
				title: '感谢使用'
			});
		},
		showError() {
			uni.showToast({
				icon: 'loading',
				title: '跳转中', //平台有差异，可能展示不全,icon设置none可以不限制文字长度
				mask: true //开启mask防止弹窗后可点击
				// duration: 1000 //展示时长ms默认约为1500ms
			});
			setTimeout(() => {
				uni.navigateTo({
					url: '/pages/demo/demo'
				});
			}, 1500);
		},
		showModal() {
			uni.showModal({
				title: '确认框',
				content: '是否确认删除',
				success() {
					console.log('确定');
				},
				fail() {
					console.log('取消');
				}
			});
		}
	},
	onLoad() {
		// uni.showLoading({
		// 	title: '数据加载中',
		// 	mask: true
		// });
		// setTimeout(() => {
		// 	// 关闭Loading框
		// 	uni.hideLoading();
		// }, 2000);
	}
};
</script>

<style lang="less">
.content {
}
</style>
