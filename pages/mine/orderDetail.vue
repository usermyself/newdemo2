<template>
	<view>
		<view class="blank"></view>
		<!-- 店铺信息 -->
		<view class="store">
			<view class="storeTop">
				<image src="../../static/stores/address.png" mode="widthFix"></image>
				<text>门店信息</text>
			</view>
			<view class="storeBottom">
				<view class="storeName">
					<text>拓冠科技1号店</text>
					<text>13710968616</text>
				</view>
				<view class="storeAddress">
					<text>广东省广州市天河区前进街道东英商务园D栋211</text>
				</view>
			</view>
		</view>
		<!-- 商品信息 -->
		<view class="store">
			<view class="storeTop">
				<image src="../../static/order/goodsDetail.png" mode="widthFix"></image>
				<text>商品信息</text>
			</view>
			<view class="goodsInfo">
				<image src="../../static/code/code.png" mode="widthFix"></image>
				<view class="info">
					<text class="goodsName">樱花莓莓酸奶</text>
					<text class="goodsEname">Cherry berry yogurt</text>
					<text class="goodsSize">默认：大/默认奶油/冰</text>
					<view class="priceNum">
						<text class="all">￥18</text>
						<text class="num">x2</text>
					</view>
				</view>
			</view>
			<view class="preferential">
				<text class="preferentialLeft">优惠券</text>
				<text class="preferentialRight">-￥20</text>
			</view>
			<view class="preferential">
				<text class="preferentialLeft">积分抵扣</text>
				<text class="preferentialRight">-￥1.66</text>
			</view>
			<view class="preferential">
				<text class="preferentialLeft">实付</text>
				<text class="price">￥28.00</text>
			</view>
		</view>
		<!-- 订单信息 -->
		<view class="store">
			<view class="storeTop">
				<image src="../../static/order/orderInfo.png" mode="widthFix"></image>
				<text>订单信息</text>
			</view>
			<view class="orderInfo">
				<text class="infoLeft">订单号</text>
				<text class="infoRight">123456</text>
			</view>
			<view class="orderInfo">
				<text class="infoLeft">获得积分</text>
				<text class="infoRight">1.66</text>
			</view>
			<view class="orderInfo">
				<text class="infoLeft">下单时间</text>
				<text class="infoRight">2020/03/03 12:30</text>
			</view>
			<view class="orderInfo">
				<text class="infoLeft">付款时间</text>
				<text class="infoRight">2020/03/03 12:30</text>
			</view>
		</view>
		<view class="blank2"></view>
		<view class="footer">
			<view class="footermain">
				<view class="button">
					<text>核销码</text>
				</view>
			</view>
			
		</view>
	</view>
</template>

<script>
</script>

<style>
	template {
		height: 100%;
		background: #f7f8fa;
	}

	page {
		height: 100%;
		background: #f7f8fa;
	}

	.blank {
		height: 20rpx;
	}

	/* 店铺信息 */

	.store {
		width: 624rpx;
		margin: 0 auto;
		background: #FFFFFF;
		padding: 0 33rpx;
		border-radius: 20rpx;
		padding-bottom: 50rpx;
		margin-bottom: 20rpx;
	}

	.storeTop {
		height: 108rpx;
		border-bottom: 1rpx dashed #ebebee;
		font-family: "PingFang SC";
		font-size: 30rpx;
		margin-bottom: 40rpx;
		display: flex;
		align-items: center;
	}

	.storeTop image {
		width: 25rpx;
		height: auto;
		display: block;
		margin-right: 19rpx;
	}

	.storeName {
		font-family: "PingFang SC";
		font-size: 28rpx;
		color: #33344A;
		margin-bottom: 24rpx;
	}

	.storeAddress {
		font-family: "PingFang SC";
		font-size: 26rpx;
		color: #999AAA;
	}

	/* 商品信息 */

	.goodsInfo {
		display: flex;
		align-items: center;
		padding-bottom: 40rpx;
		border-bottom: 1rpx dashed #ebebee;
	}

	.goodsInfo image {
		width: 180rpx;
		height: auto;
		display: block;
	}

	.info {
		width: 100%;
		font-family: "PingFang SC";
		display: flex;
		flex-direction: column;
		margin-left: 20rpx;
	}

	.goodsName {
		font-size: 32rpx;
		color: #33344A;
		margin-bottom: 5rpx;
	}

	.goodsEname {
		font-size: 20rpx;
		color: #999AAA;
		margin-bottom: 5rpx;
	}

	.goodsSize {
		font-size: 20rpx;
		color: #999AAA;
		margin-bottom: 5rpx;
	}

	.priceNum {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.all {
		font-weight: bold;
		font-size: 28rpx;
		color: #33344A;
	}

	.num {
		font-size: 24rpx;
		color: #33344A;
	}
	
	.preferential {
		margin-top: 20rpx;
		font-family: "PingFang SC";
		font-size: 26rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	
	.preferentialLeft {
		color: #999AAA;
	}
	
	.preferentialRight {
		color: #33344A;
	}
	
	.price {
		color: #EB395B;
	}
	
	/* 订单详情 */
	
	.orderInfo {
		margin-top: 20rpx;
		font-family: "PingFang SC";
		font-size: 26rpx;
		display: flex;
	}
	
	.infoLeft {
		width: 157rpx;
		display: block;
		color: #999AAA;
	}
	
	.infoRight {
		color: #33344A;
	}
	
	.footer {
		width: 100%;
		height: 112rpx;
		display: flex;
		align-items: center;
		background: #FFFFFF;
		position: fixed;
		bottom: 0;
		left: 0;
	}
	
	.footermain {
		width: 690rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		flex-flow: row-reverse;
	}
	
	.button {
		width: 200rpx;
		height: 72rpx;
		background: #EB395B;
		border-radius: 36rpx;
		font-family: "PingFang SC";
		font-size: 28rpx;
		color: #FFFFFF;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	.blank2{
		height: 100rpx;
	}
</style>
