<template>
	<view class="pubTitle">
		<!-- <view class="time">
			{{new Date(time)}}
		</view> -->
		<view class="big">
			{{title}}
		</view>
		<view class="small">
			{{subtitle}}
		</view>
		<view class="">
			{{list}}
		</view>
		<view class="line">
		</view>
	</view>
</template>

<script>
	export default {
		name: "pubTitle",
		props: {
			"title": {
				type: String,
				default: "标题"
			},
			"subtitle": {
				type: String,
				default: "副标题"
			},
			"time": {
				type: Number,
				default: Date.now()
			},
			'list': {
				type: Array,
				default () {
					return [1, 2, 3]
				}
			}
		},
		data() {
			return {

			};
		}
	}
</script>

<style lang="less">
	.pubTitle {
		padding: 60rpx 30rpx;
		text-align: center;
		background: #33FFCC;

		.big {
			font-size: 50rpx;
			font-weight: 600;
			color: #333;
		}

		.small {
			font-size: 28rpx;
			color: #888;
		}

		.line {
			height: 6rpx;
			display: inline-block;
			width: 80rpx;
			background: #1AA034;
			border-radius: 8rpx;
		}
	}
</style>
