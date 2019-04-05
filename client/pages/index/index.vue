<template>
	<view class="index-wrapper">
		<about v-if="PageCur=='about'"></about>
		<view class="cu-bar tabbar bg-white shadow foot">
			<view class="action" @click="NavChange" data-cur="about">
				<view class='icon-cu-image'>
					<image :src="'/static/tabbar/about' + [PageCur == 'about' ? '_cur' : ''] + '.png'"></image>
				</view>
				<view :class="PageCur == 'about' ? 'text-green' : 'text-gray'">我</view>
			</view>
			<view class="action" @click="NavChange" data-cur="basics">
				<view class='icon-cu-image'>
					<image :src="'/static/tabbar/basics' + [PageCur == 'basics' ? '_cur' : ''] + '.png'"></image>
				</view>
				<view :class="PageCur == 'basics' ? 'text-green' : 'text-gray'">作品</view>
			</view>
		</view>
	</view>
</template>

<script>
	import about from '@/pages/component/about.vue'
	
	export default {
		data() {
			return {
				PageCur: 'about'
			};
		},
		components:{
			about
		},
		methods: {
			NavChange: function(e) {
				this.PageCur = e.currentTarget.dataset.cur;
			}
		}
	}
</script>

<style lang="scss">
	.index-wrapper{
		padding-bottom: 100upx;
	}
</style>
