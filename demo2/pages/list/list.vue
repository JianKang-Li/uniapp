<template>
	<view class="out">
		<!-- <view v-for="item in picurl" :key="item.id"><image :src="item.url" alt="" mode="aspectFill" @click="getImg" /></view> -->
		<view @click="clickItem" class="row" v-for="item in listArr" :key="item.id">
			<view class="title">{{ item.title }}</view>
			<view class="content">{{ item.body.slice(0, 100) }}</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			// picurl: ''
			// picurl: []
			listArr: []
		};
	},
	methods: {
		getImg() {
			uni.showLoading({
				title: '数据加载中...'
			});
			uni.request({
				// url: 'https://dog.ceo/api/breeds/image/random',
				// url: 'https://api.thecatapi.com/v1/images/search',
				url: 'http://jsonplaceholder.typicode.com/posts',
				// timeout: 5000,
				// data: {
				// 	limit: 3
				// },
				success: res => {
					console.log(res);
					// console.log(res.data.message);
					// this.picurl = res.data;
					// this.picurl = res.data.message;
				},
				fail: error => {
					console.log(error);
				},
				complete() {
					uni.hideLoading();
				}
			});
		},
		getData() {
			uni.request({
				url: 'http://jsonplaceholder.typicode.com/posts',
				success: res => {
					console.log(res);
					this.listArr = res.data;
				}
			});
		},
		clickItem() {
			uni.navigateTo({
				url: '/pages/detail/detail'
			});
		}
	},
	onLoad() {
		uni.removeTabBarBadge({
			index: 1
		});
		// this.getImg();
		this.getData();
	}
};
</script>

<style lang="less">
.out {
	padding: 50rpx 30rpx;
	.row {
		padding: 20rpx 0;
		border-bottom: 1px dotted #ccc;
		.title {
			font-size: 36rpx;
			padding-bottom: 15rpx;
		}
		.content {
			font-size: 28rpx;
			color: #888;
		}
	}
}
</style>
