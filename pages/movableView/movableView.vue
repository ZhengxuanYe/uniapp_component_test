<template>
	<view class="title">
		movable-view:可移动的视图容器
	</view>

	<!-- movable-view小于movable-area -->
	<view class="section">
		<view class="section__title">movable-view区域小于movable-area</view>
		<movable-area class="movable-area-small">
			<movable-view direction="all" class="movable-view-small" x="{{x}}" y="{{y}}">
			</movable-view>
		</movable-area>
	</view>

	<!-- movable-view大于movable-area -->
	<view class="section">
		<view class="section__title">movable-view区域大于movable-area</view>
		<movable-area class="movable-area-large">
			<movable-view direction="all" class="movable-view-large">
			</movable-view>
		</movable-area>
	</view>

	<!-- 重叠的按钮 -->
	<navigator url="/pages/index/index" hover-class="none">
		<button class="overlap-button">Back to index page</button>
	</navigator>
</template>

<script setup>
	import {
		ref
	} from 'vue';

	// 初始化位置
	let x = ref(0);
	let y = ref(0);

	function moveView(newX, newY) {
		x.value = newX;
		y.value = newY;
	}
</script>

<style>
	/* 基本样式 */
	.title {
		text-align: center;
		font-size: 60rpx;
		margin-bottom: 30rpx;
	}

	.section {
		margin-top: 40rpx;
	}

	.section__title {
		text-align: center;
		font-size: 40rpx;
		margin-bottom: 20rpx;
	}

	.movable-area-small {
		height: 200px;
		width: 200px;
		background-color: #FFE567;
		position: relative;
		margin: 0 auto;
	}

	.movable-view-small {
		height: 50px;
		width: 50px;
		background-color: #CCE27D;
		position: absolute;
	}

	.movable-area-large {
		height: 100px;
		width: 100px;
		background-color: #9FE8FF;
		position: relative;
		margin: 0 auto;
	}

	.movable-view-large {
		height: 200px;
		width: 200px;
		background-color: #FFD4D9;
		position: absolute;
	}

	.overlap-button {
		position: absolute;
		width: 100%;
		bottom: 0px;
		left: 50%;
		transform: translateX(-50%);
		z-index: 1000;
	}
</style>