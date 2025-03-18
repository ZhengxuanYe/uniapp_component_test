<template>
	<view class="title">
		<text>progress:进度条</text>
	</view>
	<view class="wrapper">
		<progress :percent="percent" :show-info="isShow">
		</progress>
		<view class="display">
			<text>当前百分比:{{percent}}</text>
		</view>
		<view class="changeButton">
			<button @click="addPercent">percent++</button>
			<button @click="substractPercent"> percent--</button>
			<button @click="show_info">显示右侧百分比</button>
			<navigator url="/pages/index/index">
				<button>Back to index page</button>
			</navigator>
		</view>

	</view>
</template>
<script setup>
	import {
		ref
	} from 'vue'
	let percent = ref(50)
	let isShow = ref(false)

	function addPercent() {
		percent.value = ++percent.value;
	}

	function substractPercent() {
		percent.value = --percent.value;
	}

	function show_info() {
		isShow.value = !isShow.value;
	}
</script>

<style scoped>
	.title {
		font-size: 60rpx;
		text-align: center;
	}

	.wrapper {
		padding: 50rpx;
	}

	.display {
		margin-top: 20rpx;
		text-align: center;
	}

	.changeButton {
		margin-top: 20rpx;
	}

	button {
		width: 100%;
		margin-bottom: 10rpx;
	}
</style>