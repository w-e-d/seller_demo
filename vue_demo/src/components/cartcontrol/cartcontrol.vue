<template>
	<div class="cartcontrol">
		<div v-show="food.count>0" @click="decreaseCart" class="decrease icon-remove_circle_outline"></div>
		<div v-show="food.count>0" class="count">{{food.count}}</div>
		<div @click="addCart" class="add icon-add_circle"></div>
	</div>
</template>

<script>
	import vue from 'vue'

	export default{
		data() {
			return {
				
			}
		},

		methods: {
			addCart(event) {
				if(!event._constructed) return;
				console.log(this.food.count)
				if(!this.food.count){
					vue.set(this.food, 'count', 1)
				}else{
					this.food.count++;
				}
			},

			decreaseCart(event) {
				if(!event._constructed) return;
				if(this.food.count){
					this.food.count--;
				}
			}
		},

		props: {
			food: {
				type: Object
			}
		},

		created() {

		}
	}
</script>

<style lang="stylus">
	.cartcontrol
		display: flex
		.decrease, .add
			padding: 6px 
			line-height: 24px
			font-size: 24px
			color: rgb(0, 160, 220)
		.count
			width: 12px
			line-height: 24px
			padding-top: 6px
			font-size: 10px
			color: rgb(147, 153, 159)
</style>