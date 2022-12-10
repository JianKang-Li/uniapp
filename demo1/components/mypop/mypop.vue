<template>
	<view class="container">
		<view class="pop" v-show="show">
			<view class="head">
				<view class="item">
					<text>弹出框</text>
				</view>
				<view class="item">
					<button type="primary" size="mini" @click="close">关闭</button>
				</view>
			</view>
			<view class="content">
				这是弹出框内容
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "mypop",
		props: {
			show: {
				type: Boolean,
				default: false
			}
		},
		data() {
			return {

			};
		},
		methods: {
			close() {
				this.$emit('update:show', false)
				// this.show = false

			}
		}
	}
</script>

<style lang="less">
	.pop {
		background-color: antiquewhite;
		width: 700rpx;
		height: 500rpx;
		z-index: 1;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		display: flex;
		flex-direction: column;
		align-items: center;
		border-radius: 1rem;

		.head {
			width: 100%;
			display: flex;
			align-items: center;
			justify-content: space-evenly;
			padding-top: 10rpx;
		}

		.content {
			padding: 10rpx 0;
		}
	}
</style>
