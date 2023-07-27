<template>
	<view class="tabs">
		<scroll-view id="tab-bar" class="scroll-h" :scroll-x="scrollX" :scroll-y="scrollY">
			<view class="uni-tab-item" v-for="(item,index) in tabBars" :key="index" @click="changeTabIndex(index)">
				<text class="uni-tab-item-title" :class="currentIndex===index?'uni-tab-item-title-active':''">{{item.name}}</text>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		name:"topScrollNav",
		props:{
			tabBars:{
				type:Array,
				default:[]
			},
			currentIndex:{
				type:Number,
				default:0
			},
			scrollX:{
				type:Boolean,
				default:false
			},
			scrollY:{
				type:Boolean,
				default:false
			}
		},
		data() {
			return {
				
			};
		},
		methods:{
			changeTabIndex(index){
				this.$emit('changeTabIndex',index)
			}
		}
	}
</script>

<style>
	page {
		width: 100%;
		min-height: 100%;
		display: flex;
	}
	.tabs {
		flex: 1;
		flex-direction: column;
		overflow: hidden;
		background-color: #ffffff;
		/* height: 100vh; */
	}
	.scroll-h {
		width: 750rpx;
		width: 100%;
		height: 80rpx;
		flex-direction: row;
		white-space: nowrap;
	}

	.line-h {
		height: 1rpx;
		background-color: #cccccc;
	}

	.uni-tab-item {
		display: inline-block;
		flex-wrap: nowrap;
		padding-left: 34rpx;
		padding-right: 34rpx;
	}

	.uni-tab-item-title {
		color: #555;
		font-size: 30rpx;
		height: 80rpx;
		line-height: 80rpx;
		flex-wrap: nowrap;
		white-space: nowrap;
	}

	.uni-tab-item-title-active {
		color: #007AFF;
		border-bottom:6upx solid #ffff00;
		width:6upx;
		padding-bottom: 6upx;
	}
</style>