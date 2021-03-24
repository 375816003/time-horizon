<template>
	<view class="content">
		<timeHorizon ref='timeHorizon' @submitFun='submitFun'></timeHorizon>
	</view>
</template>

<script>
	import timeHorizon from '@/components/time-horizon/time-horizon.vue'
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		components:{
			timeHorizon
		},
		onLoad() {
			
		},
		methods: {
			submitFun(obj){
				console.log(obj)
			}
		},
		onPullDownRefresh() {
			this.$refs.timeHorizon.showMoreMonth({key:-1})
			uni.stopPullDownRefresh()
		},
		onReachBottom(){
			this.$refs.timeHorizon.showMoreMonth({key:1})
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
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
</style>
