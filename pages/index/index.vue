<template>
	<view>
		<!-- aaaa -->
		<topScrollNav scrollX='true' :tabBars="tabBars" :currentIndex="currentIndex" @changeTabIndex="changeTabIndex"></topScrollNav>
		<indexCard :indexCardList="indexCardList"></indexCard>
	</view>
</template>

<script>
	import indexCard from '@/components/indexCard/indexCard.vue'
	import topScrollNav from '@/components/topScrollNav/topScrollNav.vue'
	export default {
		components: [indexCard,topScrollNav],
		data() {
			return {
				currentIndex:0,
				indexCardList: [{
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
					}, {
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

		},
		methods: {
             changeTabIndex(index){
				 console.log(index)
				 this.currentIndex=index
			 }
		}
	}
</script>
