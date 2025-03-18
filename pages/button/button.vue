<template>
	<view class="title">
		Button:按钮
	</view>
	<view class="content">
		<button type="primary" @click="handleClick">点击我</button>

		<button class="icon-button" @click="handleIconClick">
			<uni-icons type="star-filled" size="24" color="#FFFFFF"></uni-icons>
			点击收藏
		</button>
		<button type="warn" :disabled="true">禁用按钮</button>
	</view>
	<navigator url="/pages/index/index">
		<button>Back to index page</button>
	</navigator>
</template>

<script setup>
	function handleClick() {
		console.log('按钮被点击了！');
		uni.showToast({
			title: '你点击了按钮',
			icon: 'none'
		});
	}

	function handleIconClick() {
		console.log('收藏按钮被点击了！');
		uni.showToast({
			title: '已加入收藏',
			icon: 'none'
		});
	}
</script>

<style scoped>
	.title {
		font-size: 60rpx;
		font-weight: 600;
		text-align: center;
		margin-bottom: 30rpx;
	}

	.content {
		width: 100%;
		height: 350rpx;
		display: flex;
		justify-content: space-between;
		align-center: center;
		flex-direction: column;
		margin-bottom: 20rpx;
	}

	button {
		width: 70%;
	}
</style>