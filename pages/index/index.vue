<template>
	<view class="container">
		<view class="title">
			Simple demo for uniapp component
		</view>
		<view class="instruction">
			<a href="https://zhengxuanye.github.io/">-My blog location</a>
			<a href="https://github.com/ZhengxuanYe">-My github location</a>
		</view>
		<view class="viewContainer">
			<navigator url="/pages/view/view">
				<button class="viewButton">skip to view page</button>
			</navigator>
			<navigator url="/pages/scoreView/scoreView">
				<button class="viewButton">skip to scoreView page</button>
			</navigator>

			<navigator url="/pages/swiper/swiper">
				<button class="viewButton">skip to swiper page</button>
			</navigator>
			<navigator url="/pages/movableView/movableView">
				<button class="viewButton">skip to movableView page</button>
			</navigator>

		</view>
	</view>
	<view class="basicContainer">
		<navigator url="/pages/icon/icon">
			<button class="basicButton">skip to icon page</button>
		</navigator>
		<navigator url="/pages/text/text">
			<button class="basicButton">skip to text page</button>
		</navigator>
		<navigator url="/pages/richText/richText">
			<button class="basicButton">skip to richText page</button>
		</navigator>
		<navigator url="/pages/progress/progress">
			<button class="basicButton">skip to progress page</button>
		</navigator>
	</view>
	<view class="formContainer">
		<navigator url="/pages/button/button">
			<button class="formButton">skip to button page</button>
		</navigator>
		<navigator url="/pages/checkbox/checkbox">
			<button class="formButton">skip to checkbox page</button>
		</navigator>
		<navigator url="/pages/input/input">
			<button class="formButton">skip to input page</button>
		</navigator>
		<navigator url="/pages/label/label">
			<button class="formButton">skip to label page</button>
		</navigator>
		<navigator url="/pages/textarea/textarea">
			<button class="formButton">skip to textarea page</button>
		</navigator>
		<navigator url="/pages/switch/switch">
			<button class="formButton">skip to switch page</button>
		</navigator>
	</view>
</template>

<script setup>

</script>

<style scoped>
	/* :root {
		--bg-c-yellow: #FFE567;
		--bg-c-blue: #9FE8FF;
		--bg-c-pink: #FFD4D9;
		--bg-c-green1: #F7FFC5;
		--bg-c-green2: #CCE27D;
	} */

	.container {
		display: flex;
		flex-direction: column;
		width: 750rpx;
	}

	.title,
	.instruction,
	.viewContainer,
	.basicContainer,
	.formContainer {
		width: 100%;
		box-sizing: border-box;
		padding: 10px;
		text-align: center;
	}

	.title {
		background-color: #FFE567;
		font-size: 20px;
		font-family: 'Microsoft YaHei', sans-serif;
	}

	.instruction {
		background-color: #CCE27D;
		text-decoration: none;
		border-radius: 5px;
		padding: 5px;
		transition: background-color 0.3s ease;
	}

	.instruction a {
		display: block;
	}

	.viewContainer {
		display: flex;
		flex-direction: column;
		background-color: #FFD4D9;
	}

	.viewButton {
		background-color: #F7FFC5;
	}

	.basicContainer {
		background-color: #9FE8FF;
	}

	.basicButton {
		background-color: #FFD4D9;
	}

	.formContainer {
		background-color: #F7FFC5;
	}

	.formButton {
		background-color: #FFE567;
	}
</style>