<template>
	<view>
		<view class="box" @click="change" :style="{background:bgcolor}">
			<text>{{bgcolor}}</text>
		</view>
		<view class="block" :class="{myactive:state}">

		</view>
		<view v-html="'<br/>'"></view>
		<button type="primary" size="mini" @click="state=!state">更改状态</button>
		<view class="nav">
			<view class="item" :class="{active:navIndex===index}" v-for="(item,index) in navArr" :key="item.id"
				@click="clickNav(index)">
				{{item.title}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				bgcolor: 'yellow',
				state: false,
				navArr: [{
						id: 1,
						title: "首页"
					},
					{
						id: 2,
						title: "列表"
					},
					{
						id: 3,
						title: "关于我们"
					}
				],
				navIndex: 0,
			}
		},
		methods: {
			change() {
				let color = String(Math.random()).substr(3, 6)
				this.bgcolor = `#${color}`
			},
			clickNav(index) {
				this.navIndex = index
			}
		}
	}
</script>

<style lang="less">
	.box {
		width: 150rpx;
		height: 150rpx;
		text-align: center;
		line-height: 150rpx;
		color: #ffffff;
	}

	.block {
		width: 300rpx;
		height: 300rpx;
		background: blue;
	}

	.myactive {
		width: 400rpx;
		background: hotpink;
		border-radius: 20rpx;
	}

	.nav {
		display: flex;
		justify-content: space-around;
		align-items: center;
		background-color: #eee;
		padding: 5rpx;

		.item {
			flex: 1;
			line-height: 60rpx;
			background: #ccc;
			padding: 0.3rem 1rem;
			border-radius: 0.5rem;
			cursor: pointer;
			color: #ffffff;
			text-align: center;

			&.active {
				background: #1AA034;
			}
		}
	}
</style>
