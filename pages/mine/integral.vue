<template>
	<view>
		<!-- 我的积分 -->
		<view class="big" v-if="status == 0">
			<view class="myIntegral">
				<image class="integralPic" src="../../static/integral/integral.png" mode="widthFix"></image>
				<text class="num">888</text>
				<text class="my">我的积分</text>
				<view class="button">
					<text>查看明细</text>
				</view>
			</view>
		</view>
		<!-- 积分明细 -->
		<view class="integralDetail" v-else>
			<view class="blank"></view>
			<view class="title">
				<view class="left">
					<text :class="titlestatus == 0?'active':'text'">全部</text>
					<text :class="titlestatus == 1?'active':'text'" class="spending">支出</text>
					<text :class="titlestatus == 2?'active':'text'">获取</text>
				</view>
				<picker mode="date" :value="date" :start="startDate" fields="year month" :end="endDate" @change="bindDateChange">
					<view class="right">
						<!-- <text>时间</text> -->
						<text>时间</text>
						<image src="../../static/integral/select.png" mode="widthFix"></image>
					</view>
				</picker>
			</view>

			<swiper :autoplay="false" @change="status" :style="{height: swiperHeight + 'px'}">
				<swiper-item v-for="(title, i) in titleList" :key="i">
					<scroll-view class="scroll_view" scroll-y="true" :style="{height: swiperHeight + 'px'}">
						<view class="list" v-for="(list, i) in detailList" :key="i">
							<view class="top">
								<text>{{list.name}}</text>
								<text>{{list.num}}</text>
							</view>
							<view class="bottom">
								<text>{{list.detailStatus}}</text>
								<text>{{list.time}}</text>
							</view>
						</view>
					</scroll-view>
					<view class="swiper-item"></view>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			const currentDate = this.getDate({
				format: true
			})
			return {
				status: 1, //控制导航标题
				titlestatus: 0, //明细标题
				swiperHeight: 0, //scroll高度
				titleList: ['全部', '支出', '获取'], //标题
				// date: currentDate,
				detailList: [{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					},
					{
						name: '店铺消费',
						num: '-500',
						detailStatus: '支出',
						time: '2020/03/05 20:30'
					}
				], //积分明细数组
			}
		},
		onLoad() {

		},
		onShow() {
			if (this.status == 0) {
				uni.setNavigationBarTitle({
					title: '我的积分'
				});
			} else {
				uni.setNavigationBarTitle({
					title: '积分明细'
				});
			};
			uni.getSystemInfo({
				success: (res) => {
					this.swiperHeight = (res.windowHeight - 60)
				}
			});
		},
		methods: {
			bindDateChange: function(e) {
				console.log(e)
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;

				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year + 2;
				}
				month = month > 9 ? month : '0' + month;;
				return `${year}-${month}`;
			}
		},
		computed: {
			startDate() {
				return this.getDate('start');
			},
			endDate() {
				return this.getDate('end');
			}
		}
	}
</script>

<style>
	template {
		height: 100%;
	}

	page {
		height: 100%;
		overflow: hidden;
	}

	/* 我的积分 */

	.big {
		width: 100%;
		height: 100%;
		background: #f7f8fa;
	}

	.myIntegral {
		width: 690rpx;
		border-radius: 20rpx;
		background: #FFFFFF;
		padding: 60rpx 0;
		box-shadow: 0 5rpx 5rpx #ccc;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		position: absolute;
		top: 10%;
		left: 50%;
		margin-left: -345rpx;
	}

	.integralPic {
		width: 90rpx;
		height: auto;
		display: block;
	}

	.num {
		font-family: '微软雅黑';
		font-weight: bold;
		font-size: 90rpx;
		color: #33344A;
		display: block;
		margin-top: 67rpx;
		margin-bottom: 16.5rpx;
	}

	.my {
		font-family: '微软雅黑';
		font-size: 30rpx;
		color: #33344A;
		margin-bottom: 111rpx;
	}

	.button {
		width: 610rpx;
		height: 80rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		font-family: '微软雅黑';
		font-size: 26rpx;
		color: #FFFFFF;
		background: #EB395B;
		border-radius: 40rpx;
	}

	/* 积分明细 */

	.integralDetail {
		width: 100%;
		background: #FFFFFF;
	}

	.title {
		width: 690rpx;
		margin: 0 auto;
		padding-top: 20rpx;
		margin-bottom: 20rpx;
		display: flex;
		position: fixed;
		top: 0;
		left: 50%;
		margin-left: -345rpx;
		background: #FFFFFF;
	}

	.title .left {
		width: 552rpx;
		height: 60rpx;
		font-family: "微软雅黑";
		font-size: 28rpx;
		display: flex;
	}

	.title .left text {
		width: 120rpx;
		height: 60rpx;
		display: block;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 30rpx;
	}

	.active {
		background: #eb395b;
		color: #FFFFFF;
	}

	.text {
		background: #f7f8fa;
		color: #999aaa;
	}

	.spending {
		margin: 0 10rpx;
	}

	.title .right {
		width: 138rpx;
		height: 60rpx;
		background: #f7f8fa;
		display: flex;
		align-items: center;
		justify-content: space-around;
		font-family: "微软雅黑";
		font-size: 28rpx;
		color: #33344a;
		border-radius: 30rpx;
	}

	.title .right image {
		width: 14rpx;
		height: auto;
		display: block;
	}

	.blank {
		width: 100%;
		height: 100rpx;
	}

	.list {
		width: 618rpx;
		padding: 20rpx 36rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		border-radius: 20rpx;
		box-shadow: 0 0 25rpx #edf1f4;
		margin-bottom: 20rpx;
	}

	.list .top {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: "微软雅黑";
		font-size: 28rpx;
		color: #33344A;
		margin-bottom: 20rpx;
		letter-spacing: 5rpx;
	}

	.list .bottom {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: "微软雅黑";
		font-size: 24rpx;
		color: #999AAA;
		letter-spacing: 5rpx;
	}
</style>
