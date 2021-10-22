<template>
	<view class="parent">

		<view class="content">
			<view class="top">
				<u-image width="220rpx" height="220rpx" src="~@/static/logo.png" />
				<text class="logo-text">Uni-App</text>
			</view>

			<view class="center" style="margin: 100rpx 60rpx 0 60rpx;">
				<view class="line-item">
					<text class="label">手机号:</text>
					<view class="line-item-input">
						<u-input class="input" v-model="phone" type="number" placeholder="请输入手机号" maxlength="11" />
						<u-line color="lightgray" :hair-line="true" />
					</view>
				</view>

				<view class="line-item" style="margin-top: 30rpx;">
					<text class="label">密码:</text>
					<view class="line-item-input">
						<u-input class="input1" v-model="password" type="password" placeholder="请输入密码" maxlength="16" />
						<u-line color="lightgray" :hair-line="true" />
					</view>
				</view>
			</view>

			<view class="extends">
				<u-checkbox v-model="remeber" class="remeber" labelSize="30rpx"><text
						style="color: #666666;">记住密码</text></u-checkbox>
				<text class="forget-pass">忘记密码</text>
			</view>

			<u-button class="login" type="primary" shape="circle" size="default" @click="login">登录</u-button>
		</view>

		<view class="bottom">
			<view class="blank"></view>

			<text>热啊该人为噶尔</text>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				phone: "",
				password: "123",
				remeber: false
			}
		},
		methods: {
			login: function() {

			}
		}
	}
</script>


<style>
	/* #ifndef H5 */
	page {
		height: 100%;
		background-color: #FFFFFF;
	}

	/* #endif */
</style>

<style lang="scss" scoped>
	page {
		background-color: #FFFFFF;
	}

	.parent {
		background-color: #000000;
		display: flex;
		flex-direction: column;
		justify-content: space-around;

		.content {
			flex: 1;
			margin-top: 150rpx;
			background-color: #05DFC7;
		}

		.bottom {
			background-color: #ff557f;
		}
	}

	.top {
		display: flex;
		flex-direction: column;
		align-items: center;

		.logo-text {
			margin-top: 30rpx;
			font-size: 40rpx;
			font-weight: bold;
		}
	}

	.center {
		display: flex;
		flex-direction: column;

		.label {
			width: 120rpx;
			font-size: 30rpx;
			color: #333333,
		}

		.line-item {
			display: flex;
			align-items: center;

			.line-item-input {
				flex: 1;

				.input {
					padding: 0rpx 50rpx;
				}

				.input1 {
					padding: 0rpx 150rpx;
				}
			}
		}
	}

	.extends {
		margin: 30rpx 60rpx 0 60rpx;
		display: flex;
		justify-content: space-between;
		align-items: baseline;

		.remeber {}

		.forget-pass {
			font-size: 30rpx;
			color: #666666;
		}
	}

	.login {
		font-size: 36rpx;
		font-weight: bold;
		margin: 100rpx 80rpx 0 80rpx;
	}
</style>
