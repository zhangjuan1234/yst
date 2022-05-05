<template>
	<view class="search">
		
     <!-- 输入框组件 -->
		<view class="input-group" @click="jumpToSearch">
			<uni-icons type="search" class="icon" size="25"></uni-icons>
			<input type="text" placeholder="请输入要搜索的商品" class="input">
		</view>
		 <!-- <view class="button">搜索</view> -->
		 
		 <!-- 中间 输入框 -->
		 <!-- <!-- 右边搜索按钮 -->
		 
	</view>
</template>

<script>
	export default {
		methods:{
			jumpToSearch(){
				//编程式跳转
				uni.navigateTo({
					url:"../../pages/product-search/product-search"
				})
			}
			
		}
		
	}
</script>

<style scoped lang="scss">
	.search{
		width: 750rpx;
		// border: 1px solid black;
		display: flex;
		padding: 20px 6px 6px;
		background-color: red;
		align-items: center;
		}
	.input-group{
		display: flex;
		position: relative;
		// border: 2px solid blue;
		flex: 1; 
		border-radius: 20px;
		margin: 0 6px;
		background-color: #FFF;
		/* color: red; */
		>.input{
			height: 28px;
			// border: 2px solid greenyellow;
			height: 40px;
			text-align: right;
			font-size: 16px;
			
		}
		>.icon{
			position: absolute;
			left:6px;
			top:7px;
		}
	 }
	// .button{
	// 	// border: 2px solid green;
	// 	font-size: 16px;
	// 	background-color: gainsboro;
	// 	padding: 5px;
	// 	border-radius: 5px;
	// } 
		
	

</style>