<template>
	<view>
		<myitem></myitem>
		<navigator url="/pages/index/index" open-type="reLaunch">to index</navigator>
		<form class="form" @submit="onSubmit">
			<view class="row">
				<input name="username" placeholder="姓名">
			</view>
			<view class="row">
				<textarea name="content" placeholder="内容"></textarea>
			</view>
			<view class="row">
				<radio-group name="gender">
					<text> 性别：</text>
					<label class="radio">
						<radio value="1" /><text>男</text>
					</label>
					<label class="radio">
						<radio value="0" /><text>女</text>
					</label>
					<label class="radio">
						<radio value="2" checked /><text>保密</text>
					</label>
				</radio-group>
			</view>
			<view class="row">
				<picker :range="options" name="school" @change="onChange" :value="selectValue">
					<view>
						点击选择学历：{{options[selectValue]}}
					</view>
				</picker>
			</view>
			<view class="row">
				<button type="primary" form-type="submit" size="mini">提交</button>
				<button type="default" form-type="reset" size="mini">重置</button>
			</view>
		</form>
		{{obj}}

		<input v-model="title">
		<view class="">
			原标题：{{title}}
		</view>
		<view class="">
			修改后：{{demo}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				obj: null,
				options: ["高中", "大专", "本科", "研究生", "博士"],
				selectValue: 0,
				title: ""
			};
		},
		methods: {
			onSubmit(e) {
				this.obj = e.detail.value
				this.obj.school = this.options[this.selectValue]
			},
			onChange(e) {
				this.selectValue = e.detail.value
			}
		},
		computed: {
			demo() {
				return this.title.toLocaleUpperCase()
			}
		}
	}
</script>

<style lang="less">
	input,
	textarea {
		border: 1px solid #eee;
	}

	.row {
		margin: 20rpx;
	}
</style>
