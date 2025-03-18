<template>
	<view class="rich-text-container">
		<!-- 使用 rich-text 组件来渲染富文本 -->
		<rich-text :nodes="htmlContent"></rich-text>
	</view>
	<navigator url="/pages/index/index">
		<button>Back to index page</button>
	</navigator>
</template>

<script setup>
	import {
		ref
	} from 'vue';

	// 示例富文本内容，通常这部分数据会从后端获取
	const htmlContent = ref(`
  <h1 style="color: #34495e;">rich-text:富文本</h1>
  <p>这是用 <strong>Vue 3</strong> 和 <strong>UniApp</strong> 创建的一个简单的富文本展示示例。</p>
  <p>你可以在这里添加任何HTML标签和样式，比如 <em>斜体</em> 或者 <a href="https://uniapp.dcloud.io/" target="_blank">超链接</a>。</p>
`);

	// 注意：由于安全原因，某些标签如 script 标签不会被渲染。
</script>

<style scoped>
	.rich-text-container {
		padding: 20px;
		background-color: #f9f9f9;
		border-radius: 8px;
	}
</style>