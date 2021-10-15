<template>
	<view>
		<view class="msg" @click.stop="showToast('name')"> 名字：{{msg}}，年龄：{{age}}</view>
		<view class="msg" @click="showToast('111')"> 英文名字为：{{nameEnglish}}</view>
		<slot name="content" :nick="nickname"></slot>
		<slot :user1="user"></slot>
	</view>
</template>

<script>
	export default {
		name: "test-component",
		data() {
			return {
				nickname: "Lynn",
				user: {
					"lastName": "bar",
					"firstName": "foo"
				}
			};
		},
		props: {
			msg: {
				type: String,
				default: "default msg",
				required: true
			},
			age: {
				type: Number,
				default: 22,
				validator: function(age) {
					return age > 30
				}
			},
			name: {
				type: String,
				default: 'trump'
			}
		},

		computed: {
			nameEnglish: function() {
				return this.name.toUpperCase()
			}
		},

		methods: {

			showToast(msg) {
				uni.showToast({
					title: msg,
					icon: 'none'
				});
			},
			
		}
	}
</script>

<style>
	.msg {
		font-size: 32rpx;
		font-style: italic;
		margin-top: 20rpx;
	}
</style>
