<template>
	<view>
		<view class="indexContent">
			<view class="indexAvater">
				<view>
					<image src="../../static/demo/userpic/1.jpg" mode="widthFix"></image>
					<text>鲁大师</text>
				</view>
				<view>
					<view class="guanzhu">
						<view class="icon iconfont icon-zengjia">关注</view>
					</view>
					<view class="icon iconfont icon-guanbi" color="#D5D5D5"></view>

				</view>
			</view>
			<view class="indexTitle">
				走出去才发现你跟别人差的不是一点半点
			</view>
			<view class="indexImg">
				<image src="../../static/demo/datapic/11.jpg" ></image>
				<view class="indexPlayer icon iconfont icon-bofang"></view>
				<view class="indexPlayTime">20万次播放 2:47</view>
			</view>
			<view class="indexCommit">
				<view>
					<view>
						<view class="icon iconfont icon-icon_xiaolian-mian"></view>
						<text>987</text>
					</view>
					<view>
						<view class="icon iconfont icon-icon_xiaolian-mian"></view>
						<text>987</text>
					</view>
				</view>
				<view>
					<view>
						<view class="icon iconfont icon-pinglun1"></view>
						<text>987</text>
					</view><view>
						<view class="icon iconfont icon-zhuanfa"></view>
						<text>987</text>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.indexContent{
		padding:15px;
		border-bottom:1px solid #EEEEEE;
	}
	.indexAvater{
		display:flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 15upx;;
	}
	.indexAvater uni-image{
		width:100upx;
		height:100upx;
		border-radius: 50%;
		vertical-align: middle;
		margin-right:10px;
	}
	.indexAvater uni-image> img{
		width:100%;
		height:100%;
		
	}
	.indexAvater uni-view:nth-child(2){
		display:flex;
		justify-content: flex-start;
		align-items: center;
	}
	.indexTitle{
		padding:20upx;
	}
	.guanzhu>uni-view{
		background:#F4F4F4;
		padding:6upx;
	}
	.guanzhu + uni-view{
		margin-left:16upx;
	}
	.indexImg{
		position:relative;
	}
	.indexPlayer{
		position:absolute;
		font-size: 120upx;
		color:#ffffff;
		top:50%;
		left:50%;
		margin-left:-60upx;
		margin-top:-60upx;
	}
	.indexPlayTime{
		position:absolute;
		bottom:20upx;
		right:40upx;
		background:rgba(0,0,0,.5);
		padding:8px 15px;
		border-radius: 19px;
	}
	.indexImg uni-image{
		width:100%;
		border-radius: 8upx;
	}
    .indexCommit{
		display:flex;
		justify-content: space-between;
		align-items: center;
		margin:30upx 0;
	}
	.indexCommit >uni-view{
		display:flex;
		justify-content: flex-start;
	}
	.indexCommit >uni-view>uni-view{
		display:flex;
		justify-content: flex-start;
		align-items: center;
	}
	.indexCommit >uni-view>uni-view:nth-child(2){
		margin-left:8px;
	}
	.indexCommit >uni-view>uni-view>uni-text{
		margin-left:5px;
		color:#D5D5D5;
	}
</style>