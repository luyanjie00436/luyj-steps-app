<template>
	<view>
		<uni-section title="基本用法" type="line"></uni-section>
		<view class="example-body">
			<luyj-steps :options="list1" active-color="#007AFF" :active="active" />
		</view>
		<uni-section title="纵向排列(包含分割线)" type="line"></uni-section>
		<view class="example-body">
			<luyj-steps :options="list2" active-color="#007AFF" :active="active" direction="column" />
		</view>
		<uni-section title="纵向排列(不包含分割线)" type="line"></uni-section>
		<view class="example-body">
			<luyj-steps :options="list2" :columnLine="false" active-color="#007AFF" :active="active" direction="column" />
		</view>
		<view class="word-btn" hover-class="word-btn--hover" :hover-start-time="20" :hover-stay-time="70" @click="change"><text
			 class="word-btn-white">改变状态</text></view>
	</view>
</template>

<script>
	export default {
		components: {},
		data() {
			return {
				active: 1,
				list1: [{
					title: '事件一'
				}, {
					title: '事件二'
				}, {
					title: '事件三'
				}, {
					title: '事件四'
				}],
				list2: [{
					title: '买家下单',
					desc: '2018-11-11'
				}, {
					title: '卖家发货',
					desc: '2018-11-12'
				}, {
					title: '买家签收',
					desc: '2018-11-13'
				}, {
					title: '交易完成',
					desc: '2018-11-14'
				}]
			}
		},
		methods: {
			change() {
				if (this.active < this.list1.length - 1) {
					this.active += 1
				} else {
					this.active = 0
				}
			}
		}
	}
</script>

<style lang="scss">
	@import '@/common/uni-nvue.scss';

	.status-btn {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		align-items: center;
		justify-content: center;
		height: 92rpx;
		margin: 30rpx;
		background-color: #007AFF;
	}

	.example-body {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		padding: 15px;
		flex-direction: row;
	}
</style>
