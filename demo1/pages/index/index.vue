<template>
	<view class="content">
		<pubTitle title="首页" :subtitle="'首页副标题'" :list='[4,5,6]'></pubTitle>
		<myitem></myitem>
		<navigator url="/pages/demo4/demo4?wd=uni-app&author=ljk">to demo4</navigator>
		<view style="width: 200rpx;height: 100rpx;background-color: pink;" @click="goDemo4">
			<text>api打开非导航页面</text>
		</view>
		<view style="width: 200rpx;height: 100rpx;background-color: blue;" @click="goAbout">
			<text>api打开导航页面</text>
		</view>
		<navigator url="/pages/list/list">新闻列表原始</navigator>
		<navigator url="/pages/list/list" open-type="reLaunch">to list</navigator>
		<navigator url="/pages/about/about" open-type="reLaunch">to about</navigator>

		<image src="../../static/images/16.jpeg" mode="aspectFit"></image>
		<view class="swiper">
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" circular>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/images/wallhaven-dpzww3.jpg" mode=""></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/images/797f5862373341f5abc9ee3bdb985155.jpg" mode=""></image>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item">
						<image src="../../static/images/99f9daba881111ebb6edd017c2d2eca2.jpg" mode=""></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		methods: {
			goDemo4() {
				uni.navigateTo({
					url: '/pages/demo4/demo4?wd=uniapp',
					// success: res => {
					// 	console.log(res)
					// }
				})
			},
			goAbout() {
				uni.reLaunch({
					url: '/pages/about/about?num=3',
					// success(res) {
					// 	console.log(res)
					// }
				})
			}
		}
	}
</script>

<style lang="less">
	.swiper {
		width: 100%;
		text-align: center;

		image {
			width: 100%;
		}
	}
</style>
