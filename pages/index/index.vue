<template>
	<view class="big">
		<!-- logo -->
		<view class="top" :style="{'margin-top': statusBarHeight}">
			<image class="logoPic" src="../../static/index/logo.png" mode="widthFix"></image>
			<image class="topRight" src="../../static/index/topright.png" mode="widthFix"></image>
		</view>
		<!-- 产品轮播 -->
		<view class="banner">
			<swiper class="swiper" :indicator-dots="true" :autoplay="false" :interval="3000" :duration="1000">
				<swiper-item v-for="(item, i) in bannerList" :key="i">
					<view class="swiper-item">
						<image :src="item" mode="widthFix"></image>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<!-- 我的会员 -->
		<view class="payArea">
			<view class="payTop">
				<image class="payTopPic" src="../../static/index/payTop.png" mode="widthFix"></image>
				<view class="payTopText">
					<view class="payTopLeft">
						<text class="members">我的会员</text>
						<text class="dec">Membership Privileges</text>
					</view>
					<view class="payTopRight">
						<image class="payTopRightPic" src="../../static/index/right.png" mode="widthFix"></image>
					</view>
				</view>
			</view>
			<view class="payBottom">
				<view class="payBottomFirst">
					<image class="bg" src="../../static/index/payfirst.png" mode="widthFix"></image>
					<view class="textArea">
						<view class="textAreaLeft">
							<text class="members">收藏</text>
						</view>
						<view class="textAreaRight">
							<text class="dec">Collection</text>
							<image class="textAreaRightPic" src="../../static/index/right.png" mode="widthFix"></image>
						</view>
					</view>
				</view>
				<view class="payBottomTwo">
					<image class="bg" src="../../static/index/paytwo.png" mode="widthFix"></image>
					<view class="textArea">
						<view class="textAreaLeft">
							<text class="members">优惠券</text>
						</view>
						<view class="textAreaRight">
							<text class="dec">Coupons</text>
							<image class="textAreaRightPic" src="../../static/index/right.png" mode="widthFix"></image>
						</view>
					</view>
				</view>
				<view class="payBottomThree">
					<image class="bg" src="../../static/index/paythree.png" mode="widthFix"></image>
					<view class="textArea">
						<view class="textAreaLeft">
							<text class="members">充值会员 </text>
						</view>
						<view class="textAreaRight">
							<text class="dec">Membership</text>
							<image class="textAreaRightPic" src="../../static/index/right.png" mode="widthFix"></image>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!-- 附近门店 -->
		<view class="nearStores">
			<text>附近门店</text>
		</view>
		<!-- 门店 -->
		<view class="stores">
			<scroll-view class="scroll_view" scroll-x="true">
				<block v-for="(item, i) in nearStores" :key="index">
					<view class="first">
						<view class="blank"></view>
						<view class="img"></view>
						<view class="storeName">
							<text>{{item.name}}</text>
						</view>
						<view class="storeAddress">
							<text>{{item.address}}</text>
						</view>
						<view class="more">
							<text>{{item.juli}}</text>
							<image src="../../static/index/right01.png" mode="widthFix"></image>
						</view>
						<view class="blank"></view>
					</view>
				</block>
			</scroll-view>
		</view>
		<!-- 查看更多 -->
		<view class="seeMore" @click="toStores">
			<text>查看更多</text>
			<image src="../../static/index/seemore.png" mode="widthFix"></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				statusBarHeight: 0,
				bannerList: ['../../static/index/banner.png', '../../static/index/banner.png', '../../static/index/banner.png'],
				nearStores: [{
						name: '拓冠科技1号店',
						address: '广州市天河区前进街道东英商务园D栋212',
						juli: '距离230M'
					},
					{
						name: '拓冠科技1号店',
						address: '广州市天河区前进街道东英商务园D栋212',
						juli: '距离230M'
					},
					{
						name: '拓冠科技1号店',
						address: '广州市天河区前进街道东英商务园D栋212',
						juli: '距离230M'
					}
				]
			}
		},
		onLoad() {

		},
		onShow() {
			uni.getSystemInfo({
				success: res => {
					this.statusBarHeight = res.statusBarHeight + 48 + 'px';
				}
			})
		},
		methods: {
			toStores: function() {
				uni.navigateTo({
					url: './nearStores'
				})
			}
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

	/* 清楚浮动 */

	.clearFix {
		content: '';
		display: block;
		clear: both;
	}

	/* logo区域 */
	.top {
		width: 90%;
		margin: 0 auto;
		margin-bottom: 23rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.logoPic {
		width: 200rpx;
		height: auto;
		display: block;
	}

	.topRight {
		width: 50rpx;
		height: auto;
		display: block;
	}

	/* 轮播 */

	.banner {
		width: 100%;
		height: auto;
	}

	.swiper {
		width: 100%;
		height: 500rpx;
	}

	.swiper-item {
		width: 100%;
		height: auto;
	}

	.swiper-item image {
		width: 100%;
		height: auto;
		display: block;
	}

	/* 我的会员区域 */

	.payArea {
		width: 670rpx;
		margin: 0 auto;
		border-radius: 20rpx;
		box-shadow: 0 5rpx 5rpx #ccc;
		padding: 21rpx 0;
		background: #FFFFFF;
		margin-top: 12rpx;
	}

	.payTop {
		width: 630rpx;
		margin: 0 auto;
		position: relative;
	}

	.payTopPic {
		width: 630rpx;
		display: block;
	}

	.payTopText {
		width: 90%;
		position: absolute;
		left: 50%;
		margin-left: -45%;
		bottom: 16rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.payTopLeft {
		display: flex;
		flex-direction: column;
	}

	.members {
		font-family: PingFang-SC-Medium;
		font-size: 36rpx;
		color: #FFFFFF;
	}

	.dec {
		font-family: PingFang-SC-Medium;
		font-size: 15rpx;
		color: #FFFFFF;
	}

	.payTopRightPic {
		width: 35rpx;
		height: auto;
		display: block;
	}

	/* 我的会员三部分 */

	.payBottom {
		width: 630rpx;
		margin: 0 auto;
		margin-top: 16rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
		overflow: hidden;
	}

	.payBottom>view {
		width: 200rpx;
		height: 200rpx;
		overflow: hidden;
		position: relative;
	}

	.bg {
		width: 200rpx;
		height: 200rpx;
		display: block;
	}

	.textArea {
		width: 180rpx;
		position: absolute;
		left: 50%;
		margin-left: -90rpx;
		bottom: 16rpx;
		display: flex;
		flex-direction: column;
	}

	.textAreaRight {
		height: 30rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.textAreaRightPic {
		width: 30rpx;
		height: 30rpx;
		display: block;
	}

	/* 标题附近门店 */

	.nearStores {
		width: 664rpx;
		margin: 0 auto;
		margin-top: 60rpx;
		font-family: PingFang-SC-Bold;
		font-size: 32rpx;
		color: #494949;
		/* font-weight: bold; */
	}

	/* 门店 */

	.stores {
		width: 750rpx;
		overflow-x: hidden;
	}

	.scroll_view {
		width: 690rpx;
		height: 450rpx;
		margin-left: 30rpx;
		display: flex;
		margin-top: 27rpx;
		white-space: nowrap;
		padding-right: 30rpx;
	}

	.first {
		width: 478rpx;
		background-color: #FFFFFF;
		display: inline-block;
		box-shadow: 0 10rpx 18rpx rgba(0, 0, 0, 0.2);
		border-radius: 20rpx;
		margin-left: 20rpx;
	}

	.img {
		width: 443rpx;
		height: 239rpx;
		margin: 0 auto;
		background: #000;
		border-radius: 14rpx;
	}

	.storeName {
		width: 443rpx;
		;
		font-family: PingFang-SC-Bold;
		font-size: 30rpx;
		color: #EB395B;
		margin: 19rpx auto 14rpx auto;
	}

	.storeAddress {
		width: 443rpx;
		margin: 0 auto;
		font-family: PingFang-SC-Medium;
		font-size: 19rpx;
		color: #494949;
		margin-bottom: 23rpx;
	}

	.more {
		width: 443rpx;
		height: 31rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

	.more text {
		font-family: PingFang-SC-Medium;
		font-size: 19rpx;
		color: #494949;
		padding: 9rpx 15rpx;
		background: #BFBFBF;
		border-radius: 15.5rpx;
	}

	.more image {
		width: 31rpx;
		height: auto;
		display: block;
	}

	.blank {
		width: 100%;
		height: 21rpx;
	}

	/* 查看更多 */

	.seeMore {
		width: 670rpx;
		height: 25rpx;
		margin: 0 auto;
		font-family: PingFang-SC-Medium;
		font-size: 25rpx;
		color: #494949;
		display: flex;
		align-items: center;
		padding-bottom: 20rpx;
		margin-top: 20rpx;
	}

	.seeMore image {
		width: 25rpx;
		height: auto;
		display: block;
		margin-left: 10rpx;
	}
</style>
