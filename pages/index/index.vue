<template>
	<view class="content">
		<view class="desciption">
			<view>uni-app的复制插件</view>
			<view>支持 H5、小程序、App 亲测可信</view>
			<view>如有不兼容的情况，请留言</view>
		</view>
		<view class="text-area">
			<button type="primary" @click="copy">复制</button>
		</view>
	</view>
</template>

<script>
	import uniCopy from '@/js_sdk/uni-copy/uni-copy.js'

	export default {
		methods: {
			copy() {
				let content = 'uni复制插件' 
				content = typeof content === 'string' ? content : content.toString() // 复制内容，必须字符串，数字需要转换为字符串
				const result = uniCopy(content)
				if (result === false) {
					uni.showToast({
						title: '不支持',
					})
				} else {
					uni.showToast({
						title: '复制成功',
						icon: 'none'
					})
				}
			}
		}
	}
</script>

<style>
	.content {
		max-width: 690px;
		margin: 10px auto;
		font-size: 24px;
		padding: 10px;
	}

	.desciption {
		margin: 20px auto;
		line-height: 1.8em;
	}
</style>
