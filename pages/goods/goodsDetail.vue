<template>
	<view>
		<view class="goods">
			<view class="goodsPic">
				<image src="../../static/index/banner.png" mode="widthFix"></image>
			</view>
		</view>
		<view class="goodsName">
			<text class="top">樱花莓莓酸奶</text>
			<text class="bottom">Cherry berry yogurt</text>
		</view>
	</view>
</template>

<script>
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
	
	.goodsPic {
		width: 100%;
	}
	
	.goodsPic image {
		width: 100%;
		height: auto;
		display: block;
	}
	
	.goodsName {
		width: 690rpx;
		padding: 15rpx 0;
		display: flex;
		flex-direction: column;
		justify-content: center;
		background: #FFFFFF;
		border-radius: 15rpx;
		margin: 0 auto;
		margin-top: 29rpx;
	}
	
	.goodsName .top {
		width: 90%;
		margin: 0 auto;
		font-family: '微软雅黑';
		font-size: 38rpx;
		color: #33344A;
		line-height: 40rpx;
		display: block;
	}
	
	.goodsName .bottom {
		width: 90%;
		margin: 0 auto;
		display: block;
		font-family: '微软雅黑';
		font-size: 24rpx;
		color: #999AAA;
		line-height: 26rpx;
		margin-top: 17rpx;
	}
</style>
