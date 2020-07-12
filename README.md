## uni-app三端复制插件
uni-app的复制插件，复制字符串到剪贴板，兼容三端 小程序、App、H5，试过所有三端复制插件，这个是兼容性最好的，如有不兼容的情况，请留言


### 引用方式

**js_sdk插件包文件夹放到项目的最外层（和pages文件夹同级）**

### 使用方法
```
// 引入文件
 import uniCopy from '@/js_sdk/xb-copy/uni-copy.js'
 
 export default {
 
 	methods: {
		// 触发方法
		copy() {
		   let content = 'uni复制插件' //需要复制的内容
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
 ```