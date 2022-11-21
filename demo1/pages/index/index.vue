<template>
	<view class="content">
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
	}
</script>

<style lang="less">
	.swiper{
		width: 100%;
		text-align: center;
		image{
			width: 100%;
		}
	}
</style>
