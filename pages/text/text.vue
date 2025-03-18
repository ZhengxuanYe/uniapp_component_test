<template>
	<view class="wrapper">
		<!-- 原有的内容 -->
		<view class="container">
			<view class="description">
				`text`文本组件。用于包裹文本内容。
			</view>
			<view class="display">
				<text selectable="true">这是可选文本</text>
			</view>
			<view class="display">
				<text>这是不可选文本</text>
			</view>
			<view class="display">
				<text space="emsp">这是 中文字符空格</text>
			</view>

			<view class="uni-padding-wrap uni-common-mt">
				<view class="text-box" scroll-y="true">
					<text>{{text}}</text>
				</view>
				<view class="uni-btn-v">
					<button type="primary" :disabled="!canAdd" @click="add">添加一行</button>
					<button type="warn" :disabled="!canRemove" @click="remove">移除一行</button>
				</view>
			</view>
			<navigator url="/pages/index/index">
				<button>Back to index page</button>
			</navigator>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				texts: [
					'Hello, uni-app!',
					'这是一个简单的示例。',
					'点击“添加一行”按钮增加文本行。',
					'点击“移除一行”按钮删除文本行。',
					'使用uni-app可以快速构建跨平台应用。',
					'支持iOS、Android等多个平台。',
					'......'
				],
				text: '',
				canAdd: true,
				canRemove: false,
				extraLine: []
			}
		},
		methods: {
			add() {
				this.extraLine.push(this.texts[this.extraLine.length % 6]);
				this.text = this.extraLine.join('\n');
				this.canAdd = this.extraLine.length < 6;
				this.canRemove = this.extraLine.length > 0;
			},
			remove() {
				if (this.extraLine.length > 0) {
					this.extraLine.pop();
					this.text = this.extraLine.join('\n');
					this.canAdd = this.extraLine.length < 6;
					this.canRemove = this.extraLine.length > 0;
				}
			}
		}
	}
</script>

<style scoped>
	.wrapper {
		width: 750rpx;
		height: 100vh;
		background-color: #9FE8FF;
	}

	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		width: 750rpx;
		height: 100%;
		padding: 10rpx;
	}

	.description {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 400rpx;
		height: 300rpx;
		padding: 10rpx;
	}

	.display {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 60%;
		height: 60rpx;
		background-color: pink;
		margin-bottom: 10rpx;
	}

	.display text {
		font-size: 18rpx;
		font-weight: 600;
	}

	/* 新增样式的定义 */
	.uni-padding-wrap {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		width: 100%;
		padding: 20rpx;
		box-sizing: border-box;
	}

	.uni-common-mt {
		margin-top: 20rpx;
	}

	.text-box {
		width: 100%;
		height: 300rpx;
		border: 1px solid #ccc;
		padding: 10rpx;
		margin-bottom: 20rpx;
		overflow-y: auto;
		background-color: #fff;
	}

	.uni-btn-v button {
		margin: 5rpx 0;
		width: 100%;
	}
</style>