<template>
	<view class="title">
		icon:图标
	</view>
	<view>
		<!-- 遍历所有图标类型并显示 -->
		<block v-for="iconType in iconTypes" :key="iconType">
			<view class="icon-container">
				<icon :type="iconType" size="40px" color="black" />
				<text>{{ iconType }}</text>
			</view>
		</block>
	</view>
	<navigator url="/pages/index/index">
		<button>Back to index page</button>
	</navigator>
</template>

<script setup>
	// 定义图标类型数组
	const iconTypes = [
		'success',
		'success_no_circle',
		'info',
		'warn',
		'waiting',
		'cancel',
		'download',
		'search',
		'clear'
	];
</script>

<style scoped>
	/* 添加一些样式让图标和文字排列整齐 */
	.icon-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 20px 0;
	}

	.icon-container text {
		margin-top: 10px;
	}
</style>