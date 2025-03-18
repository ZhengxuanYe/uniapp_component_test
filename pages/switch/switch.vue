<template>
	<view class="title">
		<text>Switch:开关</text>
	</view>
	<view class="wrapper">
		<view class="uni-padding-wrap uni-common-mt">
			<view class="uni-title">默认样式</view>
			<view>
				<switch checked @change="switch1Change" />
				<switch @change="switch2Change" />
			</view>
			<view class="uni-title">不同颜色和尺寸的switch</view>
			<view>
				<switch checked color="#FFCC33" style="transform:scale(0.7)" />
				<switch color="#FFCC33" style="transform:scale(0.7)" />
			</view>
			<view class="uni-title">推荐展示样式</view>
		</view>
		<view class="uni-list">
			<view class="uni-list-cell uni-list-cell-pd">
				<view class="uni-list-cell-db">开启中</view>
				<switch checked />
			</view>
			<view class="uni-list-cell uni-list-cell-pd">
				<view class="uni-list-cell-db">关闭</view>
				<switch />
			</view>
		</view>
	</view>
	<view class="description">
		<a href="https://uniapp.dcloud.net.cn/component/scroll-view.html">样例来自官方文档，有修改</a>
		<text>
			\n选择hello uni-app模板，可直接体验完整示例。
		</text>
		<navigator url="/pages/index/index">
			<button>Back to index page</button>
		</navigator>
	</view>

</template>
<script>
	export default {
		data() {
			return {}
		},
		methods: {
			switch1Change: function(e) {
				console.log('switch1 发生 change 事件，携带值为', e.detail.value)
			},
			switch2Change: function(e) {
				console.log('switch2 发生 change 事件，携带值为', e.detail.value)
			}
		}
	}
</script>
<style>
	.title {
		font-size: 60rpx;
		text-align: center;
	}

	.wrapper {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-content: center;
		height: 700rpx;
	}

	.uni-list {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-content: center;
		height: 300rpx;
	}

	.uni-common-mt {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-content: center;
		height: 400rpx;
	}

	.description {
		padding: 10rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	button {
		margin-top: 20rpx;
	}
</style>