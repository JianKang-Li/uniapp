<template>
	<view>
		<view class="">
			标题：{{title}}
		</view>
		<input v-model="title" class="input">

		--------小案例--------
		<view class="out">
			<view class="row">
				<input class="border" v-model="message.username" placeholder="请输入姓名">
			</view>
			<view class="row">
				<input class="border" v-model="message.tel" placeholder="请输入联系电话">
			</view>
			<view class="row">
				<textarea class="border" v-model="message.content" placeholder="文本域"></textarea>
			</view>
			<view class="row">
				<button type="primary" @click="onSubmit">提交</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: "学院",
				message: {
					username: "",
					tel: "",
					content: ""
				}
			};
		},
		methods: {
			onSubmit() {
				console.log(this.message)
			}
		}
	}
</script>

<style lang="less">
	.input {
		border: 1px solid #000;
		padding: 10rpx 1rem;
		width: 300rpx;
		border-radius: 0.7rem;
	}

	.out {
		padding: 30rpx;

		.row {
			margin-bottom: 10rpx;

			.border {
				border: 1px solid #eee;
				width: calc(100% - 20px);
				padding: 10px;
			}
		}


	}
</style>
