<template>
	<view>
		商品页面
		{{$attrs.title}}
		<button type="primary" @tap="handle">btn</button>
		<swiper class="swiper" circular :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
			<swiper-item>
				<image src="../../static/1.jpg" mode="aspectFit"></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/2.jpg" mode=""></image>
			</swiper-item>
			<swiper-item>
				<image src="../../static/3.jpg" mode=""></image>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		// name: "goodsItem",
		mounted() {
			console.log(this.$listeners);
		},
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 2000,
				duration: 500,
				// imgSrc: []
			}
		},
		methods: {
			handle() {
				this.$listeners.add(11)
			}
		}
	}
</script>

<style lang="scss" scoped>
.swiper{
	width: 100%;
	height: 440rpx;
	
	img{
		width: 100%;
		height: 100%;
	}
}
</style>
