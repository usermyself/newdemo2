<template>
	<view>
		<!-- 附近门店 -->
		<view class="stores" v-for="(item, i) in addressList" :key='i'>
			<view class="first">
				<view class="firstLeft">
					<view class="firmName">{{item.firmName}}</view>
					<text class="firmAddress">{{item.firmAddress}}</text>
				</view>
				<view class="firstRight">
					<text>{{item.distance}}</text>
				</view>
			</view>
			<view class="two middle">
				<image src="../../static/stores/time.png" mode="widthFix"></image>
				<text>{{item.time}}</text>
			</view>
			<view class="two finally">
				<image src="../../static/stores/address.png" mode="widthFix"></image>
				<text>{{item.address}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				addressList: [{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
					{
						firmName: '拓冠科技',
						firmAddress: '东圃商业大厦店',
						distance: '距离230M',
						time: '08:00-19:00',
						address: '广东省广州市天河区前进街道东英商务园'
					},
				]
			}
		},
		onLoad() {

		},
		onShow() {

		},
		methods: {

		},
		computed: {

		}
	}
</script>

<style>
	template {
		height: 100%;
		background: #F4F5F7;
	}

	page {
		height: 100%;
		background: #F4F5F7;
	}

	/* 附近门店 */

	.stores {
		width: 690rpx;
		margin: 0 auto;
		background: #FFFFFF;
		border-radius: 20rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 35rpx 0;
		margin-top: 20rpx;
	}

	.stores:last-child {
		margin-bottom: 20rpx;
	}

	.first {
		width: 610rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.firstLeft {
		height: 40rpx;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.firmName {
		width: 104rpx;
		height: 40rpx;
		line-height: 40rpx;
		text-align: center;
		font-family: PingFang-SC-Medium;
		color: #FFFFFF;
		font-size: 22rpx;
		background: #EB395B;
		border-radius: 7rpx;
	}

	.firmAddress {
		height: 40rpx;
		display: flex;
		align-items: center;
		font-family: PingFang-SC-Bold;
		color: #33344A;
		font-size: 26rpx;
		margin-left: 13rpx;
	}

	.firstRight {
		height: 40rpx;
		display: flex;
		align-items: center;
		font-family: PingFang-SC-Medium;
		color: #33344A;
		font-size: 30rpx;
		margin-left: 13rpx;
	}

	.two {
		width: 610rpx;
		height: 30rpx;
		display: flex;
		align-items: center;
	}

	.middle {
		margin: 24rpx auto;
	}

	.finally {
		margin: 0 auto;
	}

	.two image {
		width: 26rpx;
		height: auto;
		display: block;
		margin-right: 15rpx;
	}

	.two text {
		font-family: PingFang-SC-Medium;
		color: #999AAA;
		font-size: 24rpx;
	}
</style>
