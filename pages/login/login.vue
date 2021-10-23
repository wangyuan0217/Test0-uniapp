<template>
	<view class="content">

		<view class="top">
			<u-image width="220rpx" height="220rpx" src="~@/static/logo.png" />
			<text class="logo-text">Uni-App</text>
		</view>

		<view class="center">
			<u-field v-model="phone" label="手机号" type="number" maxlength="11" placeholder="请输入手机号" />
			<u-field v-model="password" label="密码" type="password" maxlength="16" placeholder="请输入密码" />
		</view>

		<view class="extends">
			<u-checkbox v-model="remeber" class="remeber" labelSize="30rpx"><text style="color: #666666;">记住密码</text>
			</u-checkbox>
			<text class="forget-pass">忘记密码</text>
		</view>

		<u-button class="login" type="primary" shape="circle" size="default" @click="login">登录</u-button>

		<text class="private-note">隐私协议</text>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				phone: "",
				password: "",
				remeber: false
			}
		},
		methods: {
			login: function() {
				console.log("phone = " + this.phone)
				console.log("password = " + this.password)
				console.log("remeber = " + this.remeber)
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
		height: 100%;
		background-color: #FFFFFF;
	}

	.content {
		height: 100%;
		display: flex;
		flex-direction: column;
	}

	.top {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin-top: 150rpx;

		.logo-text {
			margin-top: 30rpx;
			font-size: 40rpx;
			font-weight: bold;
		}
	}

	.center {
		display: flex;
		flex-direction: column;
		margin: 100rpx 60rpx 0 60rpx;

		// 修改父组件样式
		/deep/ .u-field {
			font-size: 28rpx;
			padding: 20rpx 0rpx;
			text-align: left;
			position: relative;
			color: $u-main-color;
		}

		/deep/ .u-label-text {
			font-size: 30rpx;
		}
	}

	.extends {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		margin: 40rpx 60rpx 0 60rpx;

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

	.private-note {
		flex-grow: 1;
		font-size: 30rpx;
		margin-bottom: 40rpx;
		color: #333333;
		display: flex;
		justify-content: center;
		align-items: flex-end;
	}
</style>
