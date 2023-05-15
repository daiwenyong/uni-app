<template>
	<view>
		<scroll-view scroll-x="true" style="white-space: nowrap;width:600rpx;box-sizing: border-box;padding-right: 20px;">
		  <view class="scroll-view-x-item" v-for="item,idx in list" :class="{active:current===idx}" @click="handleItem(item,idx)">
		  	{{$t(item.cate_name)}}
	</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		props:{
			list:{
				type:Array,
				default:[]
			}
		},
		data(){
			return {
				current:0
			}
		},
		methods:{
			handleItem(item,idx){
				this.current = idx
				this.$emit('change','b'+item.id)
			}
		}
	}
</script>

<style scoped lang="scss">

	

	.active{
		color:#fff;
		border: 1px sold #A74FBE;
		background-color: #A74FBE!important;
	}
	.scroll-view-x {
			display: flex;
			flex-wrap: nowrap;
			overflow-x: scroll;
			-webkit-overflow-scrolling: touch;
			padding-right: 20rpx;
			
		}
	  .scroll-view-x-item {
		// flex:0 0 auto;
		text-align: center;
		// padding: 10rpx;
		padding: 10rpx 20rpx;
		background-color: #f8f8f9;
		margin-right: 20rpx;
		border-radius: 24rpx;
		display: inline-block;
		box-sizing: border-box;
	  }
	  
	  
	 

</style>


