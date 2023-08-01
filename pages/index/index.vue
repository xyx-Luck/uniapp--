<template>
	<view>
		<!-- 顶部滚动导航 -->
		<topScrollNav scrollX='true' :tabBars="tabBars" :currentIndex="currentIndex" @changeTabIndex="changeTabIndex">
		</topScrollNav>
		<!-- <view class="uni-tab-bar">
			<swiper class="swiper-box" 
				:style="{height:swiperHeight+'px'}" 
				:current="current"
				@change="changeCurrent"
			>
				<swiper-item v-for="(swiper,index) in indexCardList" :key="index">
					<scroll-view scroll-y  class="list">
						<indexCard :indexCardList="swiper.list"></indexCard>
					</scroll-view>
				</swiper-item>
			</swiper>
		</view> -->
		<swiper current=0 class="swiper-box" :style="{height:swiperHeight+'px'}"  style="flex: 1;" :duration="300" @change="changeCurrent">
		    <swiper-item class="swiper-item" v-for="(tab,index) in indexCardList" :key="index">
				<scroll-view class="scroll-v list scroll-view swiper-scroll" scroll-y="true">
					<block v-for="(item,index1) in tab.list" :key="index1">
						<!-- <view>{{item}}</view> -->
						<indexCard :item="item"></indexCard>
					</block>
					
				</scroll-view>
		    </swiper-item>
		</swiper>
	</view>
</template>

<script>
	import indexCard from '@/components/indexCard/indexCard.vue'
	import topScrollNav from '@/components/topScrollNav/topScrollNav.vue'
	export default {
		components: [indexCard, topScrollNav],
		data() {
			return {
				currentIndex: 0,
				tabIndex: 0,
				swiperHeight: 0,
				indexCardList: [{
						list: [{
								avater: "../../static/demo/userpic/2.jpg",
								userName: "鲁大师",
								isFollow: false, //是否关注
								title: "走出去才发现你跟别人差的不是一点半点",
								type: "img", //img——>图片模式   video——>视频模式
								titlePic: "../../static/demo/datapic/12.jpg",
								small: {
									index: 1, //0代表没有操作，1代表顶,2代表踩；
									agree: 10,
									disagree: 10,
								},
								comment: 10, //评论
								share: 10, //分享
							},
							{
								avater: "../../static/demo/userpic/1.jpg",
								userName: "鲁大师",
								isFollow: true, //是否关注
								title: "如何用手杖改变你的一生",
								type: "video", //img——>图片模式   video——>视频模式
								titlePic: "../../static/demo/datapic/11.jpg",
								playTime: "20万", //播放次数
								videoTime: "2:47",
								small: {
									index: 2, //0:没有操作，1:顶,2:踩；
									agree: 10,
									disagree: 10,
								},
								comment: 10, //评论
								share: 10, //分享
							},
						],
						list: [{
								avater: "../../static/demo/userpic/3.jpg",
								userName: "鲁大师",
								isFollow: false, //是否关注
								title: "走出去才发现你跟别人差的不是一点半点",
								type: "img", //img——>图片模式   video——>视频模式
								titlePic: "../../static/demo/datapic/10.jpg",
								small: {
									index: 1, //0代表没有操作，1代表顶,2代表踩；
									agree: 10,
									disagree: 10,
								},
								comment: 10, //评论
								share: 10, //分享
							},
							{
								avater: "../../static/demo/userpic/4.jpg",
								userName: "鲁大师",
								isFollow: true, //是否关注
								title: "如何用手杖改变你的一生",
								type: "video", //img——>图片模式   video——>视频模式
								titlePic: "../../static/demo/datapic/11.jpg",
								playTime: "20万", //播放次数
								videoTime: "2:47",
								small: {
									index: 2, //0:没有操作，1:顶,2:踩；
									agree: 10,
									disagree: 10,
								},
								comment: 10, //评论
								share: 10, //分享
							},
						],
					},



				],
				tabBars: [{
					name: '关注',
					id: 'guanzhu'
				}, {
					name: '推荐',
					id: 'tuijian'
				}, {
					name: '体育',
					id: 'tiyu'
				}, {
					name: '热点',
					id: 'redian'
				}, {
					name: '财经',
					id: 'caijing'
				}, {
					name: '娱乐',
					id: 'yule'
				}, {
					name: '军事',
					id: 'junshi'
				}, {
					name: '历史',
					id: 'lishi'
				}, {
					name: '本地',
					id: 'bendi'
				}],
			}
		},
		onLoad() {
			//设置内容的高度
			uni.getSystemInfo({
				success: (res) => {
					const height = res.windowHeight - uni.upx2px(100)
					this.swiperHeight = height
				}
			})
		},
		methods: {
			changeTabIndex(index) {
				console.log(index)
				this.currentIndex = index
				this.tabIndex = index
			},
			changeCurrent(e) {
				console.log('swiperIndex',e.detail.current)
				this.tabIndex = e.detail.current
			}
		}
	}
</script>
<style>
	.swiper-box {
		flex: 1;
		/* height:700px; */
	}

	.swiper-item {
		flex: 1;
		flex-direction: row;
	}

	.scroll-v {
		flex: 1;
		/* #ifndef MP-ALIPAY */
		flex-direction: column;
		/* #endif */
		width: 750rpx;
		width: 100%;
	}
</style>