<template>
	<view class="emoji" :style="{height:height+'px'}">
		<view class="emoji-line" v-for="(line,i) in emoji" :key="i">
			<view @tap="clickEmoji(item)" class="emoji-line-item" v-for="(item,index) in line" :key="index">
				{{item}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			height:{
				type:Number,
				default:260
			}
		},
		data() {
			return {
				emoji:[
					['😀','😁','😂','😃','😄','😅','😆','😉'],
					['😊','😋','😎','😍','😘','😗','😙','😚'],
					['😇','😐','😑','😶','😏','😣','😥','😮'],
					['😯','😪','😫','😴','😌','😛','😜','😝'],
					['😒','😓','😔','😕','😲','😷','😖','😞'],
					['😟','😤','😢','😭','😦','😧','😨','😬'],
					['😰','😱','😳','😵','😡','😈','👹','👺'],
					['💀','👻','👽','👦','👧','👠','💩','✊'],
					['👭','💑','👪','💪','👈','👉','👊','👏'],
					['☝','👆','👇','✌','✋','👌','👍','👎'],
					['🍇','🍈','🍉','🍊','🍋','🍌','🍍','🍎'],
					['🍏','🍐','🍑','🍒','🍓','🍅','🍆','🌽'],
					['🍄','🌰','🍞','🍖','🍗','🍔','🍟','🍕'],
					['🍳','🍲','🍱','🍘','🍙','🍚','🍛','🍜'],
					['🍝','🎪','🎭','🎨','🎰','🚣','🛀','🎫'],
					['🏆','⚽','⚾','🏀','🏈','🏉','🎾','🎱'],
					['🎳','⛳','🎣','🎽','🎿','🏂','🏄','🏇'],
					['🏊','🚴','🚵','🎯','🎮','🎲','🙈','🙉'],
					],
			}
		},
		methods: {
			//获取表情并发送
			clickEmoji:function(e){
				this.$emit('emotion',e);
			}
		}
	}
</script>

<style lang="scss">
.emoji{
	width: 100%;
	// height: 460rpx;
	padding: 16rpx 12rpx 180rpx 12rpx;
	box-sizing: border-box;
	overflow:hidden;
	overflow-y: auto;
	.emoji-line{
		display: flex;
		.emoji-line-item{
			flex:1;
			text-align: center;
			font-size: 42rpx;
			line-height: 68rpx;
		}
	}
}
</style>
