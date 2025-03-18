<template>
	<view>
		<view class="title">
			textarea多行文本输入框
		</view>
		<view class="wrapper">
			<view class="input">
				<!-- 使用textarea代替原来的input -->
				<textarea v-model="textareaContent" placeholder="请输入多行文本" />
			</view>
			<view class="output">
				<text>您输入的内容是: {{ textareaContent }}</text>
			</view>
			<button @click="deleteValue">清空内容</button>
		</view>
		<navigator url="/pages/index/index">
			<button>返回首页</button>
		</navigator>
	</view>
</template>

<script setup>
	import {
		ref
	} from 'vue';

	const textareaContent = ref('');

	function deleteValue() {
		textareaContent.value = ''; // 清空输入框的内容
	}
</script>

<style>
	.title {
		font-size: 40rpx;
		font-weight: 600;
		text-align: center;
	}

	.wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-around;
		width: 100%;
		height: 500rpx;
	}

	.input {
		width: 80%;
		height: 40%;
		background-color: #FFD4D9;
		padding: 20rpx;
		box-sizing: border-box;
		/* 确保padding不会增加元素的实际宽度和高度 */
	}

	.output {
		width: 90%;
		height: 30%;
		background-color: #9FE8FF;
		padding: 20rpx;
		box-sizing: border-box;
		word-break: break-all;
		/* 当一行内无法放下时进行换行 */
	}
</style>