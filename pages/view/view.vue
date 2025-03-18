<template>
	<view class="wrapper">
		<view class="container">
			<view class="description">
				<text>

					它类似于传统html中的div，用于包裹各种元素内容。

					如果使用nvue，则需注意，包裹文字应该使用text组件。
				</text>
			</view>
			<view class="box1">
				<view class="box2" :hover-class="{ 'active-box2': 'isActive' }">
				</view>
			</view>
			<button @click="toggleActive">
				add hover class to box2
			</button>
			<navigator url="/pages/index/index">
				<button>Back to index page</button>
			</navigator>
		</view>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue';


	const isActive = ref(false);
	const isPropagation = ref(false);

	// 定义点击事件处理函数
	function toggleActive() {
		isActive.value = !isActive.value;
	}
</script>

<style>
	.wrapper {
		width: 750rpx;
		height: 100vh;
		background-color: #F7FFC5;
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
		width: 600rpxrpx;
		height: 300rpx;
		padding: 10rpx;
	}

	.box1 {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 300rpx;
		height: 300rpx;
		background-color: skyblue;
		margin-bottom: 20rpx;
	}

	.box2 {
		width: 100rpx;
		height: 100rpx;
		background-color: chocolate;
	}

	/* 定义激活状态下的 box2 样式 */
	.active-box2 {
		background-color: #8bc34a;
		transform: scale(1.2);
	}

	button {
		margin-bottom: 20rpx;
	}
</style>