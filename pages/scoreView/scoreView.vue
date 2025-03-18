<template>
	<view>
		<view class="uni-padding-wrap uni-common-mt">
			<view class="uni-title uni-common-mt">
				Vertical Scroll
				<text>\n纵向滚动
				</text>
			</view>
			<view>
				<scroll-view :scroll-top="scrollTop" scroll-y="true" class="scroll-Y" @scrolltoupper="upper"
					@scrolltolower="lower" @scroll="scroll">
					<view id="demo1" class="scroll-view-item uni-bg-red">A</view>
					<view id="demo2" class="scroll-view-item uni-bg-green">B</view>
					<view id="demo3" class="scroll-view-item uni-bg-blue">C</view>
				</scroll-view>
			</view>
			<view @tap="goTop" class="uni-link">
				点击这里返回顶部
			</view>

			<view class="uni-title uni-common-mt">
				Horizontal Scroll
				<text>\n横向滚动</text>
			</view>
			<view>
				<scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="120">
					<view id="demo1" class="scroll-view-item_H uni-bg-red">A</view>
					<view id="demo2" class="scroll-view-item_H uni-bg-green">B</view>
					<view id="demo3" class="scroll-view-item_H uni-bg-blue">C</view>
				</scroll-view>
			</view>
			<view class="uni-common-pb"></view>
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

	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		methods: {
			upper: function(e) {
				console.log(e)
			},
			lower: function(e) {
				console.log(e)
			},
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				// 解决view层不同步的问题
				this.scrollTop = this.old.scrollTop
				this.$nextTick(function() {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style>
	/* :root {
		--bg-c-yellow: #FFE567;
		--bg-c-blue: #9FE8FF;
		--bg-c-pink: #FFD4D9;
		--bg-c-green1: #F7FFC5;
		--bg-c-green2: #CCE27D;
	} */
	.uni-title {
		margin-bottom: 10rpx;
		font-size: 60rpx;
	}

	.uni-link {
		margin: 15rpx auto;
		text-align: center;
		text-decoration: black;
		background-color: pink;
	}

	.scroll-Y {
		height: 300rpx;
	}

	.scroll-view_H {
		white-space: nowrap;
		width: 100%;
	}

	.scroll-view-item {
		height: 300rpx;
		line-height: 300rpx;
		text-align: center;
		font-size: 36rpx;
	}

	.scroll-view-item_H {
		display: inline-block;
		width: 100%;
		height: 300rpx;
		line-height: 300rpx;
		text-align: center;
		font-size: 36rpx;
	}

	#demo1 {
		background-color: #9FE8FF;
	}

	#demo2 {
		background-color: #FFD4D9;
	}

	#demo3 {
		background-color: #F7FFC5;
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