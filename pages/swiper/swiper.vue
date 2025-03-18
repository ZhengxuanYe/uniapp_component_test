<template>
	<view class="title">
		Swiper:滑块视图容器
	</view>
	<view class="wrapper">
		<view class="swiper">
			<swiper :indicator-dots="isDots" :autoplay="isAutoplay" :interval="3000" :duration="1000">
				<swiper-item>
					<view class="swiper-item1">
						<text>item1</text>
					</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item2">
						<text>item2</text>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="changeButton">
			<button @click="changeAutoplay">关闭自动播放</button>
			<button @click="changeDots">关闭面板指示点</button>
		</view>
		<navigator url="/pages/index/index">
			<button>Back to index page</button>
		</navigator>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue'
	let isDots = ref(true);
	let isAutoplay = ref(true);

	function changeAutoplay() {
		isAutoplay.value = !isAutoplay.value;
	}

	function changeDots() {
		isDots.value = !isDots.value;
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
	.title {
		font-size: 60rpx;
		margin-bottom: 30rpx;
	}

	.swiper {
		width: 100%;
		height: 400rpx;
	}


	.swiper-item1 {
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #9FE8FF;
		height: 100%;
		width: 100%;
		font-size: 60rpx;
	}

	.swiper-item2 {
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #FFD4D9;
		height: 100%;
		width: 100%;
		font-size: 60rpx;
	}
</style>