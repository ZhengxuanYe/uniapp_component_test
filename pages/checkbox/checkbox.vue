<template>
	<view class="title">
		<text>checkbox：多选框</text>
	</view>
	<view class="wrapper">

		<view class="box1">
			<view>默认样式</view>
			<view>
				<checkbox-group>
					<label>
						<checkbox value="cb1" :checked="true" />选中
					</label>
					<label>
						<checkbox value="cb2" />未选中
					</label>
				</checkbox-group>
			</view>

			<view>不同颜色和尺寸的checkbox</view>
			<view>
				<checkbox-group>
					<label>
						<checkbox value="cb3" :checked="true" color="#FFCC33" style="transform:scale(0.7)" />选中
					</label>
					<label>
						<checkbox value="cb4" color="#FFCC33" style="transform:scale(0.7)" />未选中
					</label>
				</checkbox-group>
			</view>
		</view>

		<view class="uni-padding-wrap">
			<view class="uni-title uni-common-mt">
				<text>\n使用 uni-list 布局</text>
			</view>
		</view>
		<view>
			<checkbox-group @change="checkboxChange">
				<label v-for="item in items" :key="item.value">
					<view>
						<checkbox :value="item.value" :checked="item.checked" />
					</view>
					<view>{{item.name}}</view>
				</label>
			</checkbox-group>
		</view>
	</view>
	<navigator url="/pages/index/index">
		<button>Back to index page</button>
	</navigator>
</template>

<script>
	export default {
		data() {
			return {
				items: [{
						value: 'cb5',
						name: '选项一',
						checked: true
					},
					{
						value: 'cb6',
						name: '选项二',
						checked: false
					},
					{
						value: 'cb7',
						name: '选项三',
						checked: false
					}
				]
			};
		},
		methods: {
			checkboxChange(e) {
				console.log('改变后的值为：', e.detail.value);
				// 这里可以添加逻辑来处理复选框状态的变化
			}
		}
	};
</script>

<style>
	.wrapper {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
		height: 900rpx;
	}

	.title {
		font-size: 60rpx;
		text-align: center;
	}

	.box1 {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
		height: 400rpx;
	}
</style>