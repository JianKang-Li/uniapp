<template>
	<view>
		<view>
			当前标题{{title}}
			<rich-text nodes="<br/>"></rich-text>
			数组{{arr[1]}}
		</view>
		
		--------v-html------
		<view  v-html="title"></view>
		<view v-html="code"></view>
		<h2>小程序</h2>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title:"uni小程序",
				arr:[1,2,3],
				code:"<h1>uniapp联系</h1>"
			};
		}
	}
</script>

<style lang="less">

</style>
