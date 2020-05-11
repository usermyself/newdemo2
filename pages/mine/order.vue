<template>
	<view>
		<!-- 标题 -->
		<view class="title">
			<view class="part" v-for="(item, i) in titleList" :key='i' @click="choose" :data-i="i">
				<text :class="current == i?'is':'no'">{{item}}</text>
				<view :class="current == i?'underline':'nounderline'"></view>
			</view>
		</view>
		<swiper class="swiper" :autoplay="false" :style="{height: swiperHeight + 'px'}" @change="swiper" :current="current">
			<swiper-item v-for="(item, i) in titleList" :key='i'>
				<view class="swiper-item">
					<scroll-view scroll-y="true" :style="{height: swiperHeight + 'px'}">
						<view class="list" v-for="(item, i) in orderList" :key='i'>
							<view class="basicInfo">
								<text class="basicLeft">订单号：{{item.orderNum}}</text>
								<text class="basicRight">{{item.orderStatus}}</text>
							</view>
							<view class="goodsOrder" v-for="(list, n) in item.goodsList" :key='n'>
								<view class="goodsOrderLeft">
									<image src="../../static/code/code.png" mode="widthFix"></image>
								</view>
								<view class="goodsOrderRight">
									<text class="goodsName">{{list.goodsName}}</text>
									<text class="goodsSize">{{list.goodsSize}}</text>
								</view>
							</view>
							<view class="settlement">
								<view class="settlementLeft">
									<text>{{item.time}}</text>
								</view>
								<view class="settlementRight">
									<text class="together">共{{item.num}}件，合计</text>
									<text class="num">￥{{item.price}}</text>
								</view>
							</view>
							<view class="button">
								<view class="pay" v-if="item.orderStatus == '待付款'">
									<text>立即付款</text>
								</view>
								<view class="cancel" v-if="item.orderStatus == '待付款'">
									<text>取消订单</text>
								</view>
								<view class="pay" v-if="item.orderStatus == '待使用'" @click="showCancelCode">
									<text>核销码</text>
								</view>
								<view class="pay" v-if="item.orderStatus == '已完成' || item.orderStatus == '已取消'">
									<text>删除订单</text>
								</view>
							</view>
						</view>
					</scroll-view>
				</view>
			</swiper-item>
		</swiper>
		<!-- 核销码 -->
		<view class="cancelCode" v-if="cancelCode" @click="showCancelCode">
			<view class="cancelMain">
				<view class="cancelTitle">
					<text>核销码</text>
				</view>
				<view class="codePic">
					<image src="../../static/code/code.png" mode="widthFix"></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				current: 0, //标题当前状态
				titleList: ['全部', '待付款', '待使用', '已完成', '已取消'], //标题数组
				swiperHeight: 0, //轮播高度
				cancelCode: true, //核销码
				orderList: [{
					orderNum: '123456',
					orderStatus: '待付款',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					},
					{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 2,
					price: '56.00',
				},
				{
					orderNum: '123456',
					orderStatus: '待使用',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 1,
					price: '56.00',
				},
				{
					orderNum: '123456',
					orderStatus: '已完成',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					},
					{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					},
					{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 3,
					price: '56.00',
				},
				{
					orderNum: '123456',
					orderStatus: '已取消',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 1,
					price: '56.00',
				},
				{
					orderNum: '123456',
					orderStatus: '待付款',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 1,
					price: '56.00',
				},
				{
					orderNum: '123456',
					orderStatus: '待付款',
					goodsList: [{
						goodsName: '樱花莓莓酸奶',
						goodsSize: '大/默认奶油/冰',
					}],
					time: '2020/04/08 12:30',
					num: 1,
					price: '56.00',
				}]
			}
		},
		onLoad() {

		},
		onShow() {
			this.getSwiperHeight()
		},
		methods: {
			//手动选择查看内容
			choose: function (e) {
				this.current = e.currentTarget.dataset.i
			},
			//显示核销码
			showCancelCode: function () {
				this.cancelCode = !this.cancelCode
			},
			//获取滑块
			swiper: function (e) {
				this.current = e.detail.current
			},
			//获取轮高度
			getSwiperHeight() {
				uni.getSystemInfo({
					success: (res) => {
						this.swiperHeight = (res.windowHeight - 57)
					}
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
		background: #f7f8f9;
	}

	page {
		height: 100%;
		background: #f7f8f9;
	}

	/* 标题 */

	.title {
		width: 100%;
		height: 94rpx;
		display: flex;
		align-items: center;
		justify-content: space-around;
		background: #FFFFFF;
	}

	.part {
		flex: 1;
		height: 94rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		position: relative;
		font-family: "PingFang SC";
		color: #33344A;
		font-size: 28rpx;
	}

	.underline {
		width: 40rpx;
		height: 6rpx;
		position: absolute;
		left: 50%;
		margin-left: -20rpx;
		bottom: 0;
		background: #FF496B;
	}
	
	.nounderline {
		width: 40rpx;
		height: 6rpx;
		position: absolute;
		left: 50%;
		margin-left: -20rpx;
		bottom: 0;
		background: #FFFFFF;
	}
	
	.is {
		font-weight: bold;
	}
	
	.no {
		font-weight: normal;
	}
	
	/* 订单列表 */
	
	.swiper {
		width: 100%;
		margin-top: 20rpx;
	}
	
	.list {
		width: 650rpx;
		margin: 0 auto;
		border-radius: 20rpx;
		background: #FFFFFF;
		padding: 20rpx 20rpx;
		box-shadow: 0 0 30rpx #e9edf2;
		margin-bottom: 20rpx;
		padding-top: 0;
	}
	
	.basicInfo {
		width: 100%;
		height: 96rpx;
		border-bottom: 1rpx dashed #EBEBEE;
		font-family: "微软雅黑";
		font-size: 26rpx;
		margin-bottom: 18rpx;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	
	.basicLeft{
		color: #33344A;
	}
	
	.basicRight {
		color: #E93A5A;
	}
	
	.goodsOrder {
		width: 100%;
		display: flex;
		margin-bottom: 20rpx;
	}
	
	.goodsOrderLeft {
		margin-right: 19rpx;
	}
	
	.goodsOrderLeft image {
		width: 100rpx;
		height: auto;
		border-radius: 10rpx;
		display: block;
	}
	
	.goodsOrderRight {
		display: flex;
		flex-direction: column;
		justify-content: center;
		font-family: "PingFang SC";
	}
	
	.goodsName {
		font-size: 30rpx;
		color: #33344A;
	}
	
	.goodsSize {
		font-size: 24rpx;
		color: #999AAA;
		margin-top: 17rpx;
	}
	
	.settlement {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: "PingFang SC";
		font-size: 24rpx;
	}
	
	.settlementLeft {
		color: #999AAA;
	}
	
	.settlementRight {
		display: flex;
		align-items: center;
	}
	
	.together {
		color: #33344A;
	}

	.num {
		color: #E93A5A;
		display: block;
		margin-left: 5rpx;
	}
	
	.button {
		width: 100%;
		height: 68rpx;
		margin-top: 40rpx;
		display: flex;
		flex-flow: row-reverse;
	}
	
	.button view {
		width: 170rpx;
		height: 68rpx;
		border: 1rpx solid #e0e1e5;
		border-radius: 35rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		font-family: "PingFang SC";
		font-size: 26rpx;
		color: #67677A;
	}
	
	.cancel {
		margin-right: 20rpx;
	}
	
	/* 核销码 */
	
	.cancelCode {
		width: 100%;
		height: 100%;
		position: fixed;
		top: 0;
		left: 0;
		background: rgba(0,0,0,0.5);
		display: flex;
		align-items: center;
		justify-content: center;
	}
	
	.cancelMain {
		width: 440rpx;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 60rpx 70rpx 100rpx 70rpx;
		border-radius: 10rpx;
		background: #FFFFFF;
	}
	
	.cancelTitle {
		width: 460rpx;
		margin: 0 auto;
		font-family: "PingFang SC";
		font-size: 32rpx;
		color: #33344A;
		font-weight: bold;
		text-align: center;
		line-height: 32rpx;
		margin-bottom: 50rpx;
	}
	
	.cancelTitle text {
		line-height: 32rpx;
	}
	
	.codePic {
		width: 460rpx;
		height: 460rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 5rpx;
		background: #F7F8F9;
	}
	
	.codePic image {
		width: 360rpx;
		height: 360rpx;
		display: block;
	}
</style>
