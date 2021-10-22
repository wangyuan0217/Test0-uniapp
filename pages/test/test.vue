<template>
	<view class="content">

		<image class="logo" src="/static/logo.png" @click="test"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>

		<view v-for="(item,index) in 3">
			<text class="title"> {{item}} : {{index}}</text>
		</view>

		<button @click="add1('123233432212312', $event)" class="title">Add 1</button>
		<text class="title">次数为：{{count}}</text>

		<input v-model="message" placeholder="edit me">
		<text>Message is: {{ message }}</text>



		<picker :range="array" :value="index" @change="valueChanged">
			<text>当前选择：{{array[index]}}</text>
		</picker>


		<radio-group class='radio-group' @change="radioChange">
			<label class='radio-group-item' v-for="(item, index) in items" :key="item.name">
				<radio :value="item.name" :checked="item.checked" /> {{item.value}}
			</label>
		</radio-group>

		<view class="text-area">
			<text class="title">{{reverseTitle}}</text>
		</view>

		<test-component msg="张三" :age="33" name="lynn" @click.native="showToast('点击了子组件')">
			<template #content="contentSlot">
				<view class="title">这是父组件 slot 的值：{{ contentSlot.nick }}</view>
			</template>
			<template v-slot="defaultSlot">
				<view class="title">这是父组件默认slot的内容 {{ defaultSlot.user1.lastName }}</view>
			</template>
		</test-component>


	<u-button v-text="1111111"></u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: getApp().globalData.url,
				count: 1,
				index: 0,
				message: '2122',
				array: ['111', '222', '33', '444', '55', '23'],
				items: [{
						name: 'USA',
						value: '美国'
					},
					{
						name: 'CHN',
						value: '中国',
						checked: 'true'
					},
					{
						name: 'BRA',
						value: '巴西'
					}
				],
				list: [
					['A', 'B', 'C'],
					['D', 'E', 'F'],
					['G', 'H', 'I']
				]
			}
		},

		onLoad() {

		},

		computed: {
			reverseTitle: {
				get() {
					return this.title + '-' + this.count
				},
				// setter
				set(newValue) {
					console.log("newValue = " + newValue)
					var arr = newValue.split(' ')
					this.title = arr[0]
					this.count = arr[1]
				}
			}
		},

		watch: {

		},

		methods: {

			add1(msg, event) {
				uni.showToast({
					title: '点击了',
					icon: 'none'
				})
				this.count += 1
				this.title += this.count
				this.reverseTitle = 'ab cd'
			},

			valueChanged(e) {
				this.index = e.target.value
			},

			radioChange(e) {
				console.log('radio发生change事件，携带value值为：', e.target.value)
			},

			test: function() {
				
			},
			
			showToast: function(msg) {
				uni.showToast({
					title: msg,
					icon: 'none'
				});
			}

		},




	}
</script>

<style scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}


	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 20rpx;
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

	.radio-group {
		margin: 15rpx 150rpx;
	}

	.radio-group-item {
		margin-left: 15rpx;
		margin-right: 15rpx;
	}
</style>
