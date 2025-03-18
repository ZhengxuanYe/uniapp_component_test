<template>
	<view>
		<!-- 复选框组，表单组件位于label内 -->
		<view class="uni-common-mt">
			<view class="uni-form-item uni-column">
				<view class="title">表单组件在label内</view>
				<checkbox-group class="uni-list" @change="checkboxChange">
					<label class="uni-list-cell uni-list-cell-pd" v-for="item in checkboxItems" :key="item.name">
						<view>
							<checkbox :value="item.name" :checked="item.checked"></checkbox>
						</view>
						<view>{{item.value}}</view>
					</label>
				</checkbox-group>
			</view>

			<!-- 单选按钮组，使用for标识表单组件 -->
			<view class="uni-form-item uni-column">
				<view class="title">label用for标识表单组件</view>
				<radio-group class="uni-list" @change="radioChange">
					<label class="uni-list-cell uni-list-cell-pd" v-for="(item, index) in radioItems" :key="index">
						<view>
							<radio :id="item.name" :value="item.name" :checked="item.checked"></radio>
						</view>
						<view>
							<label class="label-2-text" :for="item.name">
								<text>{{item.value}}</text>
							</label>
						</view>
					</label>
				</radio-group>
			</view>

			<!-- label内有多个表单组件时，默认选中第一个 -->
			<view class="uni-form-item uni-column">
				<view class="title">label内有多个时选中第一个</view>
				<checkbox-group class="uni-list" @change="checkboxChange">
					<label class="label-3">
						<view class="uni-list-cell uni-list-cell-pd">
							<checkbox value="选项一">选项一</checkbox>
						</view>
						<view class="uni-list-cell uni-list-cell-pd">
							<checkbox value="选项二">选项二</checkbox>
						</view>
						<view class="uni-link uni-center" style="margin-top:20rpx;">点击这句文字默认选中第一个checkbox</view>
					</label>
				</checkbox-group>
			</view>
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
				checkboxItems: [{
						name: 'cb1',
						value: '选项1',
						checked: false
					},
					{
						name: 'cb2',
						value: '选项2',
						checked: true
					}
				],
				radioItems: [{
						name: 'rd1',
						value: '选项A',
						checked: false
					},
					{
						name: 'rd2',
						value: '选项B',
						checked: true
					}
				]
			};
		},
		methods: {
			checkboxChange(e) {
				console.log('checkbox发生change事件，携带value值为：', e.detail.value);
			},
			radioChange(e) {
				console.log('radio发生change事件，携带value值为：', e.detail.value);
			}
		}
	};
</script>

<style scoped>
	/* 样式部分可以根据需要自行定义 */
	.uni-common-mt {
		margin-top: 20px;
	}

	.uni-form-item {
		margin-bottom: 20px;
	}

	.title {
		font-weight: bold;
		margin-bottom: 10px;
	}

	.uni-list-cell {
		padding: 10px 0;
	}

	.label-3 .uni-list-cell-pd:first-child input[type="checkbox"] {
		/* 确保第一个checkbox被选中 */
		background-color: lightblue;
	}

	.uni-column {
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 30rpx;
	}
</style>