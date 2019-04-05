<template>
	<view class = "about-wrapper">
		<swiper class="screen-swiper round-dot" :indicator-dots="true" :circular="true" :autoplay="true" interval="5000"
		 duration="500">
			<swiper-item v-for="(item,index) in 4" :key="index">
				<image :src="'https://ossweb-img.qq.com/images/lol/web201310/skin/big3900'+index+ '.jpg'" mode="aspectFill"></image>
			</swiper-item>
		</swiper>
		<view class = "desc-wrapper">
			<view class="cu-bar bg-white">
				<view class="action">
					<text class="icon-titles text-green"></text>
					<text class="text-xl text-bold">我的时间轴</text>
				</view>
			</view>
		</view>
		<view class = "timeline-wrapper">
			<view class="cu-timeline">
				<view class="cu-time">2018-06</view>
				<view class="cu-item text-blue">
					<view class="bg-blue content shadow-blur">
						就职于【国泰基金管理有限公司】，担任高级前端开发工程师，主要负责公司直销平台以及代销产品的全栈开发
					</view>
				</view>
				<view class="cu-time">2017-05</view>
				<view class="cu-item">
					<view class="bg-cyan content shadow-blur">
						就职于【阅文集团】，担任前端开发工程师，主要负责NOAH活动模板引擎（中台）以及起点读书各类运营H5页面的开发
					</view>
				</view>
				<view class="cu-time">2016-10</view>
				<view class="cu-item">
					<view class="content">
						玩起了公众号运营，建立了【胖乌鸦的巢】，研究一些公众号运营的方法，会发表一些矫情的文章
					</view>
				</view>
				<view class="cu-time">2015-07</view>
				<view class="cu-item">
					<view class="bg-cyan content shadow-blur">
						就职于【腾讯科技深圳有限公司】，担任全栈开发工程师，主要负责公司内部站点的开发
					</view>
				</view>
				<view class="cu-time">2015-07</view>
				<view class="cu-item">
					<view class="content bg-green shadow-blur">
						毕业于【四川大学】-软件工程专业
					</view>
				</view>
				<view class="cu-time">2014-12</view>
				<view class="cu-item">
					<view class="bg-cyan content shadow-blur">
						就职于成都【SAP】【实习生】，从事SuccessFactor的开发，主要使用JAVA进行WEB开发
					</view>
				</view>
				<view class="cu-time">2014-03</view>
				<view class="cu-item">
					<view class="bg-cyan content shadow-blur">
						就职于【腾讯科技深圳有限公司】【实习生】，从事内部应用的开发
					</view>
				</view>
				<view class="cu-time">2011-09</view>
				<view class="cu-item">
					<view class="content">
						进入【四川大学】软件工程专业，开始苦逼的程序员大学生活
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

			};
		}
	}
</script>

<style lang="scss">
	.about-wrapper{
	}
</style>
