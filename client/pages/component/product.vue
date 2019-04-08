<template>
	<view class = "product-wrapper">
		<view class = "list-wrapper">
			<view class = "product-item"
				v-for = "(product,index) in productList" :key = "index">
				<view class="cu-bar bg-white solid-bottom">
					<view class="action">
						<text class="icon-titles text-blue"></text> {{product.name}}
					</view>
				</view>
				<view class="cu-card dynamic no-card">
					<view class="cu-item shadow">
						<view class="text-content">
							{{product.desc}}
						</view>
						<view class="text-content">
							<view class='flex flex-wrap'>
								<view class = "padding-xs"
									 v-for = "(tag, tagIndex) in product.tags" :key = "tagIndex">
									 <view class='cu-tag bg-blue round'>{{tag}}</view>
								</view>
							</view>
						</view>
						<view class="grid flex-sub padding-lr col-3 grid-square">
							<view class="bg-img" :style="{'background-image': 'url(' + image + ')'}"
							 v-for="(image, imgIndex) in product.images" :key="imgIndex" @tap = "showModal(image)">
							</view>
						</view>
						<view class="text-gray text-sm text-right padding">
						</view>
					</view>
				</view>
			</view>
		</view>
		<view class="cu-modal" :class="isShowModal ? 'show' : ''">
			<view class="cu-dialog">
				<view class="bg-img" :style="{'background-image': 'url(' + currentImageSrc + ')'}">
					<view class="cu-bar justify-end text-white">
						<view class="action" @tap="hideModal">
							<text class="icon-close "></text>
						</view>
					</view>
				</view>
				<view class="cu-bar bg-white">
					<view class="action margin-0 flex-sub  solid-left" @tap="hideModal">关闭</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isShowModal: false,
				currentImageSrc: '',
				productList: [
					{
						name: '国泰基金 支付宝小程序',
						desc: '国泰基金各类运营活动「支付宝小程序」',
						tags: [
							'支付宝小程序',
							'uni-app (跨端框架)',
							'Node'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_4.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_5.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_6.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_7.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_8.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/alipay_9.png'
						]
					},
					{
						name: '国泰基金 Hybrid APP',
						desc: '基于Android + Crosswalk + Vue的国泰基金Hybrid App的开发（目前已经在各大应用市场上线）',
						tags: [
							'Android',
							'CrossWalk',
							'ASimpleCache',
							'Glide',
							'Vue 全家桶',
							'Webpack',
							'Axios'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_4.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_5.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_6.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_7.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_8.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtapp_9.png'
						]
					},
					{
						name: '国泰基金 直销官网',
						desc: '基于ThinkPHP + JQuery的国泰基金官网改造和迭代',
						tags: [
							'ThinkPHP',
							'JQuery',
							'Gulp'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtfund_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtfund_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtfund_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gtfund_4.png'
						]
					},
					{
						name: '国泰基金 H5运营活动',
						desc: '各类基于VUE的运营H5活动开发，主要服务于支付宝中的「国泰基金财富号」',
						tags: [
							'Vue 全家桶',
							'Webpack',
							'Axios',
							'云凤蝶',
							'Hilo (阿里H5游戏引擎)'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_4.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_5.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/gth5_6.png'
						]
					},
					{
						name: '国泰基金 内部工具',
						desc: '基于Electron的国泰内部工具的开发',
						tags: [
							'Electron',
							'Bootstrap3'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/electron_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/electron_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/electron_3.png'
						]
					},
					{
						name: '阅文集团 Noah活动模板引擎',
						desc: '起点侧的运营活动频繁，部署效率低，人力少，但是活动模块可复用性强，但是无平台将这些模块进行统一整理和配置，NOAH能够使得产品经理灵活配置活动的上线时间，下线时间以及活动的基本数据，一键式部署，不再传统部署流程 ',
						tags: [
							'Vue 全家桶',
							'SeaJS',
							'JQuery',
							'Webpack',
							'Gulp'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_4.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_5.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_6.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/noah_7.png',
						]
					},
					{
						name: '腾讯科技 面试官移动WEB助手',
						desc: '面试官移动助手旨在微信侧提供WEB移动端系统辅助面试官进行简历的筛选，学生叫号通知，待办已办事项查看，面试环节提交等功能，帮助面试官在移动端快速进行学生面试后的数据线上化提交步骤',
						tags: [
							'Vue 全家桶',
							'JQuery',
							'Webpack',
							'PHP YAF',
							'Redis',
							'Mysql'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_4.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_5.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_6.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_7.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_8.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_9.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_10.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_11.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/helper_12.png'
						]
					},
					{
						name: '腾讯科技 校园招聘内网管理系统',
						desc: '重构招聘内网管理系统',
						tags: [
							'Vue 全家桶',
							'JQuery',
							'Webpack',
							'.NET Framework4',
							'Redis',
							'SQL Server'
						],
						images: []
					},
					{
						name: '腾讯科技 校园招聘官网',
						desc: '校园招聘官网',
						tags: [
							'Smarty',
							'JQuery',
							'PHP YAF',
							'Memcache',
							'Redis',
							'Mysql'
						],
						images: [
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/tencent_1.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/tencent_2.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/tencent_3.png',
							'https://uniapp-1251340574.cos.ap-shanghai.myqcloud.com/tencent_4.png'
						]
					}
				]
			};
		},
		methods: {
			showModal(imageSrc) {
				this.currentImageSrc = imageSrc;
				this.isShowModal = true;
			},
			hideModal() {
				this.isShowModal = false;
			}
		}
	}
</script>

<style lang="scss">
	.product-wrapper{
		.list-wrapper{
			.product-item{
				margin: 20upx;
				
				.text-content{
					margin-top: 20upx;
				}
			}
		}
		
		.cu-dialog{
			.bg-img{
				height: 800upx;
				background-size: contain;
			}
		}
	}
</style>
