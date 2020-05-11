<template>
	<view class="bg">
		<!-- vip -->
		<view class="vipArea" v-if="status == 0">
			<view class="vip">
				<image class="vipPic" src="../../static/index/banner.png"></image>
				<view class="isVip">
					<view class="left">
						<text class="current">当前余额</text>
						<text class="num">3000</text>
					</view>
					<view class="right">
						<view :class="isVip == 0?'nocode':'code'">
							<text>付款码</text>
						</view>
						<view :class="isVip == 0?'norecord':'record'">
							<text>消费记录</text>
						</view>
					</view>
				</view>
			</view>
			<view class="top_up">
				<view class="title">
					<text>会员卡充值</text>
				</view>
				<view class="choose">
					<view class="part">
						<view class="partTop">
							<text class="priceLeft">￥</text>
							<text class="priceRight">100</text>
						</view>
						<view class="partBottom">
							<text>充100得120</text>
						</view>
					</view>
					<view class="part">
						<view class="partTop">
							<text class="priceLeft">￥</text>
							<text class="priceRight">100</text>
						</view>
						<view class="partBottom">
							<text>充100得120</text>
						</view>
					</view>
					<view class="part">
						<view class="partTop">
							<text class="priceLeft">￥</text>
							<text class="priceRight">100</text>
						</view>
						<view class="partBottom">
							<text>充100得120</text>
						</view>
					</view>
				</view>
				<view class="button">
					<text>立即充值</text>
				</view>
			</view>
		</view>
		<!-- 付款码 -->
		<view class="payCode" v-else>
			<view class="main">
				<view class="scanCode">
					<text>付款码</text>
				</view>
				<image class="codePic" src="../../static/code/code.png" mode="widthFix"></image>
				<view class="payWay">
					<view class="wayLeft">
						<text class="wayTop">VIP卡支付</text>
						<text class="wayBottom">当前余额：￥100.00</text>
					</view>
					<view class="wayRight">
						<image src="../../static/code/right.png" mode="widthFix"></image>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				status: 1, //是否显示付款码
				isVip: 1, //是否是会员
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
		background-color: #f7f8f9;
	}
	
	page {
		height: 100%;
		background-color: #f7f8f9;
	}
	
	.bg {
		height: 100%;
	}
	
	/* 充值vip */
	
	.vipArea {
		padding-top: 20rpx;
	}
	
	.vip {
		width: 690rpx;
		margin: 0 auto;
		border-radius: 20rpx;
		position: relative;
	}
	
	.vipPic {
		width: 690rpx;
		height: 392rpx;
		display: block;
		border-radius: 20rpx;
	}
	
	.isVip {
		width: 632rpx;
		height: 100rpx;
		display: flex;
		background: rgba(0, 0, 0, 0.5);
		align-items: center;
		justify-content: space-between;
		padding: 0 29rpx;
		position: absolute;
		bottom: 0;
		left: 0;
		border-bottom-left-radius: 20rpx;
		border-bottom-right-radius: 20rpx;
	}
	
	.isVip .left {
		flex: 1;
		display: flex;
		align-items: center;
	}
	
	.current {
		font-family: "微软雅黑";
		font-size: 22rpx;
		color: #FFFFFF;
		display: block;
		margin-right: 14rpx;
	}
	
	.num {
		font-family: "微软雅黑";
		font-size: 38rpx;
		color: #FFFFFF;
	}
	
	.isVip .right {
		flex: 1;
		display: flex;
		align-items: center;
	}
	
	.isVip .right view {
		width: 140rpx;
		height: 56rpx;
		border-radius: 28rpx;
		font-family: "微软雅黑";
		font-size: 26rpx;
		display: flex;
		align-items: center;;
		justify-content: center;
	}
	
	.isVip .right .code {
		background: #FFFFFF;
		color: #eb395b;
		margin-right: 20rpx;
	}
	
	.isVip .right .nocode {
		background: #FFFFFF;
		color: #999aaa;
		margin-right: 20rpx;
	}
	
	.isVip .right .record {
		background: #eb395b;
		color: #FFFFFF;
	}
	
	.isVip .right .norecord {
		background: #999aaa;
		color: #FFFFFF;
		margin-right: 20rpx;
	}
	
	/* 充值 */
	
	.top_up {
		width: 660rpx;
		margin: 0 auto;
		padding: 40rpx 15rpx;
		border-radius: 10rpx;
		background-color: #FFFFFF;
		margin-top: 40rpx;
	}
	
	.choose {
		width: 630rpx;
		margin: 0 auto;
		display: flex;
		flex-wrap: wrap;
		align-items: center;
		justify-content: space-between;
	}
	
	.part {
		width: 184rpx;
		height: 194rpx;
		border-radius: 20rpx;
		border: 3rpx solid #EB395B;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-bottom: 20rpx;
	}
	
	.partTop {
		margin-bottom: 27rpx;
	}
	
	.priceLeft {
		font-family: "微软雅黑";
		font-size: 24rpx;
		color: #EB395B;
		font-weight: bold;
	}
	
	.priceRight {
		font-family: "微软雅黑";
		font-size: 32rpx;
		color: #EB395B;
		font-weight: bold;
	}
	
	.partBottom {
		width: 142rpx;
		height: 38rpx;
		text-align: center;
		background: #fef4ef;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 10rpx;
		font-family: "微软雅黑";
		font-size: 20rpx;
		color: #FA9563;
		font-weight: bold;
	}
	
	.partBottom text {
		line-height: 20rpx;
		display: block;
	}
	
	.title {
		width: 630rpx;
		margin: 0 auto;
		margin-top: 20rpx;
		margin-bottom: 30rpx;
		font-family: '微软雅黑';
		font-size: 34rpx;
		font-weight: 500;
		color: #000000;
	}
	
	.button {
		width: 630rpx;
		height: 80rpx;
		margin: 0 auto;
		text-align: center;
		line-height: 80rpx;
		font-family: "微软雅黑";
		font-size: 28rpx;
		color: #FFFFFF;
		background: #EB395B;
		border-radius: 40rpx;
		margin-top: 60rpx;
	}
	
	/* 付款码 */
	
	.payCode {
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		background: #EB395B;
	}
	
	.main {
		width: 630rpx;
		margin: 0 auto;
		padding-top: 80rpx;
		border-radius: 20rpx;
		background: #FFFFFF;
	}
	
	.scanCode {
		width: 100%;
		text-align: center;
		font-family: "微软雅黑";
		font-size: 32rpx;
		color: #33344A;
		font-weight: bold;
		margin-bottom: 80rpx;
	}
	
	.codePic {
		width: 420rpx;
		height: auto;
		display: block;
		margin: 0 auto;
		margin-bottom: 120rpx;
	}
	
	.payWay {
		width: 550rpx;
		height: 140rpx;
		background-color: #F9FAFB;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0 40rpx;
		border-bottom-left-radius: 20rpx;
		border-bottom-right-radius: 20rpx;
	}
	
	.wayLeft {
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
	
	.wayTop {
		margin-bottom: 20rpx;
		font-family: "微软雅黑";
		font-size: 32rpx;
		font-weight: bold;
		color: #33344A;
	}
	
	.wayBottom {
		font-family: "微软雅黑";
		font-size: 26rpx;
		font-weight: bold;
		color: #999AAA;
	}
	
	.wayRight image {
		width: 12rpx;
		height: auto;
		display: block;
	}
</style>
