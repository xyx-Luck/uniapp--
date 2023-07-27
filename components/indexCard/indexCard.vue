<template>
	<view>
		<view class="indexContent" v-for="(item,index) in indexCardList">
			<view class="indexAvater">
				<view>
					<image :src="item.avater" mode="widthFix"></image>
					<text>{{item.userName}}</text>
				</view>
				<view>
					<view class="guanzhu">
						<view :class="item.isFollow==false?'icon iconfont icon-zengjia':'active'">
							{{item.isFollow==false?'关注':'已关注'}}</view>
					</view>
					<view class="icon iconfont icon-guanbi" color="#D5D5D5"></view>
		
				</view>
			</view>
			<view class="indexTitle">
				{{item.title}}
			</view>
			<view class="indexImg">
				<image :src="item.titlePic"></image>
				<template v-if="item.type!='img'">
					<view class="indexPlayer icon iconfont icon-bofang"></view>
					<view class="indexPlayTime">{{item.playTime}}次播放 {{item.videoTime}}</view>
				</template>
			</view>
			<view class="indexCommit">
				<view>
					<view>
						<view :class="item.small.index==1?'icon iconfont icon-icon_xiaolian-mian active':'icon iconfont icon-icon_xiaolian-mian' "></view>
						<text>{{item.small.agree}}</text>
					</view>
					<view>
						<view class="icon iconfont icon-kulian"></view>
						<text>{{item.small.disagree}}</text>
					</view>
				</view>
				<view>
					<view>
						<view class="icon iconfont icon-pinglun1"></view>
						<text>{{item.comment}}</text>
					</view>
					<view>
						<view class="icon iconfont icon-zhuanfa"></view>
						<text>{{item.share}}</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"indexCard",
		props:{
		  	indexCardList:{
				type:Array,
				default:[]
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style>
	.indexContent {
		padding: 15px;
		border-bottom: 1px solid #EEEEEE;
	}

	.indexAvater {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 15upx;
		;
	}

	.indexAvater uni-image {
		width: 100upx;
		height: 100upx;
		border-radius: 50%;
		vertical-align: middle;
		margin-right: 10px;
	}

	.indexAvater uni-image>img {
		width: 100%;
		height: 100%;

	}

	.indexAvater uni-view:nth-child(2) {
		display: flex;
		justify-content: flex-start;
		align-items: center;
	}

	.indexTitle {
		padding: 20upx;
	}

	.guanzhu>uni-view {
		background: #F4F4F4;
		padding: 6upx;
	}
    .guanzhu>uni-view.active{
		background: #00ff00;
		padding: 6upx;
		color:#ffffff
	}
	.guanzhu+uni-view {
		margin-left: 16upx;
	}

	.indexImg {
		position: relative;
	}

	.indexPlayer {
		position: absolute;
		font-size: 120upx;
		color: #ffffff;
		top: 50%;
		left: 50%;
		margin-left: -60upx;
		margin-top: -60upx;
	}

	.indexPlayTime {
		position: absolute;
		bottom: 20upx;
		right: 40upx;
		background: rgba(0, 0, 0, .5);
		padding: 8px 15px;
		border-radius: 19px;
	}

	.indexImg uni-image {
		width: 100%;
		border-radius: 8upx;
	}

	.indexCommit {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin: 30upx 0;
	}

	.indexCommit>uni-view {
		display: flex;
		justify-content: flex-start;
	}

	.indexCommit>uni-view>uni-view {
		display: flex;
		justify-content: flex-start;
		align-items: center;
	}

	.indexCommit>uni-view>uni-view:nth-child(2) {
		margin-left: 8px;
	}
    .indexCommit>uni-view>uni-view>uni-view{
		color:#D5D5D5;
	}
	dexCommit>uni-view>uni-view>uni-view.active{
		color:#f8ec63;
	}
	.indexCommit>uni-view>uni-view>uni-text {
		margin-left: 5px;
		color: #D5D5D5;
	}
</style>