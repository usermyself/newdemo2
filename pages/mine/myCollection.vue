<template>
	<view>
		<view class="choose">
			<view class="title" v-for="(item, i) in titleList" :key="i">
				<text :class="current === i ? 'activeText':'titleText'">{{item}}</text>
				<view :class="current === i ? 'active':'nor'"></view>
			</view>
		</view>
		<view class="blank"></view>
		<view class="chooseMain">
			<swiper class="swiper" :autoplay="false" @change="swiper" :style="{height: swiperHeight + 'px'}">
				<swiper-item v-for="(titleMain, i) in titleList" :key="i">
					<view class="swiper-item">
						<scroll-view class="goods" scroll-y="true" v-if="current === 0" :style="{height: swiperHeight + 'px'}">
							<view class="list" v-for="(goodsList, i) in goodsList" :key='i'>
								<view class="left">
									<image :src="goodsList.goodsPic" mode="widthFix"></image>
								</view>
								<view class="middle">
									<text class="name">{{goodsList.goodsName}}</text>
									<text class="englishName">{{goodsList.goodsEname}}</text>
									<text class="size">{{goodsList.goodsSize}}</text>
									<text class="price">{{goodsList.goodsPrice}}</text>
								</view>
								<view class="right">
									<image src="../../static/collection/delete.png" mode="widthFix"></image>
								</view>
							</view>
						</scroll-view>
						<scroll-view class="cstores" scroll-y="true" v-if="current === 1" :style="{height: swiperHeight + 'px'}">
							<view class="stores" v-for="(item, i) in storesList" :key='i'>
								<view class="first">
									<view class="firstLeft">
										<view class="firmName">{{item.firmName}}</view>
										<text class="firmAddress">{{item.firmAddress}}</text>
									</view>
									<view class="firstRight">
										<text>{{item.distance}}</text>
									</view>
								</view>
								<view class="two middle2">
									<image src="../../static/stores/time.png" mode="widthFix"></image>
									<text>{{item.time}}</text>
								</view>
								<view class="two finally">
									<image class="address" src="../../static/stores/address.png" mode="widthFix"></image>
									<text class="addressText">{{item.address}}</text>
									<image class="deletePic" src="../../static/collection/delete.png" mode="widthFix"></image>
								</view>
							</view>
						</scroll-view>
					</view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				titleList: ['收藏商品', '收藏门店'],
				current: 0,
				goodsList : [{
					goodsPic: '../../static/index/payfirst.png',
					goodsName: '樱花莓莓酸奶',
					goodsEname: 'Cherry berry yogurt',
					goodsSize: '默认：大/默认奶油/冰',
					goodsPrice: '￥18',
					
				},
				{
					goodsPic: '../../static/index/payfirst.png',
					goodsName: '樱花莓莓酸奶',
					goodsEname: 'Cherry berry yogurt',
					goodsSize: '默认：大/默认奶油/冰',
					goodsPrice: '￥18',
					
				},
				{
					goodsPic: '../../static/index/payfirst.png',
					goodsName: '樱花莓莓酸奶',
					goodsEname: 'Cherry berry yogurt',
					goodsSize: '默认：大/默认奶油/冰',
					goodsPrice: '￥18',
					
				},
				{
					goodsPic: '../../static/index/payfirst.png',
					goodsName: '樱花莓莓酸奶',
					goodsEname: 'Cherry berry yogurt',
					goodsSize: '默认：大/默认奶油/冰',
					goodsPrice: '￥18',
					
				},
				{
					goodsPic: '../../static/index/payfirst.png',
					goodsName: '樱花莓莓酸奶',
					goodsEname: 'Cherry berry yogurt',
					goodsSize: '默认：大/默认奶油/冰',
					goodsPrice: '￥18',
					
				}],
				storesList: [{
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
				],
				swiperHeight: 0
			}
		},
		onLoad() {

		},
		onShow() {
			uni.getSystemInfo({
				success: (res) => {
					this.swiperHeight = (res.windowHeight - 47)
				}
			})
		},
		methods: {
			swiper: function(e) {
				this.current = e.detail.current
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

	/* 标题选择 */

	.choose {
		width: 100%;
		height: 94rpx;
		background: #FFFFFF;
		display: flex;
		align-items: center;
		justify-content: center;
		position: fixed;
		top: 0;
		left: 0;
	}

	.blank {
		height: 94rpx;
	}

	.title {
		flex: 1;
		height: 94rpx;
		font-family: '微软雅黑';
		font-size: 30rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
	}

	.titleText {
		font-weight: normal;
	}

	.activeText {
		color: #33344A;
		font-weight: bold;

	}

	.active {
		width: 40rpx;
		height: 6rpx;
		background: #FF496B;
		position: absolute;
		bottom: 0;
		left: 50%;
		margin-left: -20rpx;
	}

	.nor {
		width: 40rpx;
		height: 6rpx;
		background: #FFFFFF;
		position: absolute;
		bottom: 0;
		left: 50%;
		margin-left: -20rpx;
	}

	,

	/* 收藏列表 */

	.chooseMain {
		height: 100%;
	}

	.swiper-item {
		height: 100%;
	}

	.cstores {
		height: 100%;
	}

	.list {
		width: 628rpx;
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 20rpx 31rpx;
		border-radius: 20rpx;
		background: #FFFFFF;
		margin-bottom: 20rpx;
	}
	
	.list:first-child {
		margin-top: 20rpx;
	}

	.middle {
		min-width: 350rpx;
		display: flex;
		flex-direction: column;
	}

	.left image {
		width: 150rpx;
		height: 150rpx;
		display: block;
	}

	.middle text {
		display: block;
	}

	.name {
		font-family: '微软雅黑';
		font-size: 32rpx;
		color: #33344A;
		font-weight: bold;
	}

	.englishName {
		font-family: '微软雅黑';
		font-size: 20rpx;
		color: #999AAA;
		margin: 6rpx 0;
	}

	.size {
		font-family: '微软雅黑';
		font-size: 20rpx;
		color: #999AAA;
		margin-bottom: 13.5rpx;
	}

	.price {
		font-family: '微软雅黑';
		font-size: 28rpx;
		color: #FF496B;
		font-weight: bold;
	}

	.right image {
		width: 34rpx;
		height: auto;
		display: block;
	}

	/* 收藏门店 */

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
		font-family: '微软雅黑';
		color: #FFFFFF;
		font-size: 22rpx;
		background: #EB395B;
		border-radius: 7rpx;
	}

	.firmAddress {
		height: 40rpx;
		display: flex;
		align-items: center;
		font-family: '微软雅黑';
		color: #33344A;
		font-size: 26rpx;
		margin-left: 13rpx;
	}

	.firstRight {
		height: 40rpx;
		display: flex;
		align-items: center;
		font-family: '微软雅黑';
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

	.middle2 {
		margin: 24rpx auto;
	}

	.finally {
		margin: 0 auto;
	}

	.middle2 image {
		width: 26rpx;
		height: auto;
		display: block;
		margin-right: 15rpx;
	}

	.two text {
		font-family: '微软雅黑';
		color: #999AAA;
		font-size: 24rpx;
	}
	
	.address {
		width: 26rpx;
		height: auto;
		display: block;
		margin-right: 15rpx;
	}
	
	.deletePic {
		width: 31rpx;
		height: auto;
		display: block;
	}
	
	.addressText {
		width: 510rpx;
		display: block;
	}
</style>
