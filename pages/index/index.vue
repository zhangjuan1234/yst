<template>
	<view class="content">
		<!-- f1:输入框 -->
		<view class="text-area">
			<yst-heafer></yst-heafer>
		</view>
		<!-- f2: 轮播图-->
		<view>我是轮播图，待完善</view>
		<!-- f3:分类 -->
		<view>我是分类，待完善</view>
		<!-- f4: 提示-->
		<view>我是滚动的提示，待完善</view>
		<!-- f5:卡片主体 -->
		<view>


			<uni-grid :column="2" :highlight="true" @change="change" :showBorder="false" :square="false">
				<uni-grid-item v-for="(p, i) in products" :key="i">
					<uni-card :is-shadow="true" padding="0" margin="6rpx">
						<image :src="`${p.imgUrl}`" class="image"></image>
						<view class="title">{{p.name}}</view>
						<view class="price">零售价:￥{{p.originalPrice}}</view>
					</uni-card>

				</uni-grid-item>
			</uni-grid>


		</view>


	</view>
</template>

<script>
	export default {
		data() {
			return {
				products: []

			}
		},
		onLoad() {
			this.getData()
		},
		methods: {
			getData() {
				uni.showLoading({
					title: "页面正在加载"
				})
				let url = 'https://ycstapi.100qu.net/api/goods/productList'
				uni.request({
					url,
					method: 'POST',
					data: {
						"channel": "ycst",
						"pageIndex": 1,
						"pageSize": 10,
						"orderAsc": 1,
						"orderBy": 3
					},
					success: res => {
						console.log(res.data)
						this.products = res.data.apiResult.data
					},
					fail: err => {
						console.log(err)
					},
					complete: () => {
						console.log('成功失败都要执行')
						uni.hideLoading()
					}
				})

			}

		}
	}
</script>

<style scoped lang="scss">
	.image {
		width: 325rpx;
		height: 325rpx;
		border: 1px solid gainsboro;
		display: block;
		margin: 15rpx auto;
	}

	.title {
		font-size: 18px;
		// 2行
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-line-clamp: 2; //（多行：改这）
		-webkit-box-orient: vertical;

	}

	.price {
		font-size: 14px;
		color: red;
	}
</style>
