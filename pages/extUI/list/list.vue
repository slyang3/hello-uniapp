<template>
	<view>
		<view class="example-title">基本用法</view>
		<uni-list>
			<uni-list-item title="标题文字" show-arrow="false"></uni-list-item>
			<uni-list-item title="标题文字"></uni-list-item>
			<uni-list-item title="标题文字" show-badge="true" badge-text="12"></uni-list-item>
			<uni-list-item title="禁用状态" disabled="true" show-badge="true" badge-text="12"></uni-list-item>
		</uni-list>
		<view class="example-title">包含描述信息</view>
		<uni-list>
			<uni-list-item title="标题文字" note="描述信息" show-arrow="false"></uni-list-item>
			<uni-list-item title="标题文字" note="描述信息"></uni-list-item>
			<uni-list-item title="标题文字" note="描述信息" show-badge="true" badge-text="12"></uni-list-item>
		</uni-list>
		<view class="example-title">显示缩略图</view>
		<uni-list>
			<uni-list-item title="标题文字" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
			<uni-list-item title="标题文字" note="描述信息" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png"></uni-list-item>
		</uni-list>
		<view class="example-title">显示扩展图标</view>
		<uni-list>
			<uni-list-item title="标题文字" show-extra-icon="true" :extra-icon="extraIcon1"></uni-list-item>
			<uni-list-item title="标题文字" note="描述信息" show-extra-icon="true" :extra-icon="extraIcon2"></uni-list-item>
		</uni-list>
		<view class="example-title">显示Switch</view>
		<uni-list>
			<uni-list-item title="标题文字" show-switch="true" show-arrow="false" @switchChange="switchChange"></uni-list-item>
			<uni-list-item title="标题文字" show-switch="true" switch-checked="true" show-arrow="false" @switchChange="switchChange"></uni-list-item>
			<uni-list-item title="禁用状态" disabled="true" show-switch="true" switch-checked="true" show-arrow="false" @switchChange="switchChange"></uni-list-item>
		</uni-list>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'

	export default {
		components: {
			uniList,
			uniListItem
		},
		data() {
			return {
				extraIcon1: {
					color: '#007aff',
					size: '22',
					type: 'info-filled'
				},
				extraIcon2: {
					color: '#4cd964',
					size: '22',
					type: 'spinner'
				}
			};
		},
		methods: {
			switchChange(e) {
				uni.showToast({
					title: 'change:' + e.value,
					icon: 'none'
				})
			}
		}
	}
</script>

<style>
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #fff
	}

	view {
		font-size: 28upx;
		line-height: inherit
	}

	.example {
		padding: 0 30upx 30upx
	}

	.example-title {
		font-size: 32upx;
		line-height: 32upx;
		color: #777;
		margin: 40upx 25upx;
		position: relative
	}

	.example .example-title {
		margin: 40upx 0
	}

	.example-body {
		padding: 0 40upx
	}
</style>