<template>
	<view class="content">
		<button type="primary" @click="showSuccess">showSuccess</button>
		<button type="warn" @click="showError">showError</button>
		<view class=""><navigator url="/pages/demo/demo">跳转到demo页面</navigator></view>
		<view class=""><button @click="showModal">showModal</button></view>
		<view class=""><button @click="showActive">showActive</button></view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			arr: ['三国演义', '水浒传', '红楼梦', '西游记']
		};
	},
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
				title: '手机严重',
				// content: '是否确认删除',
				editable: true,
				placeholderText: '请输入手机号',
				success(res) {
					if (res.confirm) {
						console.log('确定', res);
					} else if (res.cancel) {
						uni.showToast({
							title: '取消',
							icon: 'none'
						});
					}
				},
				fail(error) {
					console.log('error', error);
				}
			});
		},
		showActive() {
			uni.showActionSheet({
				// title: '名著选择',
				itemList: this.arr,
				// 存在this指向问题
				success: res => {
					console.log('选中了' + this.arr[res.tapIndex], res);
				},
				fail: res => {
					console.log(res.errMsg);
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
	},
	onTabItemTap() {
		uni.hideTabBarRedDot({
			index: 0
		});
	}
};
</script>

<style lang="less">
.box {
	width: 200rpx;
	height: 200rpx;
	background-color: antiquewhite;
}
</style>
