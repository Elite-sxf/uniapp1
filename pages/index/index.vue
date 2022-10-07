<template>
	<view class="content">
		<uni-nav-bar shadow title="淘宝商场"/>
		
		<scroll-view class="topBar" scroll-x="true" show-scrollbar="false">
			<view class="scroll-view-item" v-for="(item,index) in titleNav" :key="index" @tap="changeTab(index)">
				<text :class="topBarIdx === index ? 'selected':''">{{item.name}}</text>
			</view>
		</scroll-view>
		
		<goods-item :title="title" @add="add"></goods-item>
		
	</view>
</template>

<script>
	import goodsItem from "@/components/goods/goods.vue";
	export default {
		components: {
			goodsItem:goodsItem,
		},
		data() {
			return {
				title: 'Hello',
				titleNav: [
					{name: "推荐"},
					{name: "运动户外"},
					{name: "服饰内衣"},
					{name: "鞋靴包包"},
					{name: "美妆个护"},
					{name: "家具数码"},
					{name: "食品母婴"},
				],
				topBarIdx: 0,  //选中bar的index
			}
		},
		onLoad() {
			console.log("111")
			// var a = new Promise((resolve,reject) =>{
			// 	// resolve(1)
			// 	reject("err")
			// })
			// a.then((v)=> {
			// 	console.log(v)
			// }).catch((v)=>{
			// 	console.log(v);
			// })
		},
		methods: {
			add(v) {
				console.log(v);
				// this.$refs.popup.open('top')
			},
			
			changeTab(index) {
				this.topBarIdx = index;
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		/* display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center; */
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
	
	.topBar {
		width: 100%;
		height: 100rpx;
		white-space: nowrap;
		
		.scroll-view-item {
			display: inline-block;
			padding: 20rpx 40rpx;
			text-align: center;
			font-size: 36rpx;
			
		}
		
		.selected {
			padding: 20rpx 0;
			border-bottom: 2px #55ffff solid;
			color: #55ffff;
		}
	}
	/deep/ .uni-scroll-view::-webkit-scrollbar {
		display: none;
		height: 0 !important;
		background-color: transparent;
	}
	
</style>
