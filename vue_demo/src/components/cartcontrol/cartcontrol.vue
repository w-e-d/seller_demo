<template>
	<div class="cartcontrol">
		<transition class="decrease-wrapp" name="move">
			<div v-show="food.count>0" @click.stop="decreaseCart" class="decrease">
				<span class="inner icon-remove_circle_outline"></span>
			</div>
		</transition>
		<div v-show="food.count>0" class="count">{{food.count}}</div>
		<div @click.stop="addCart" class="add">
			<span class="inner icon-add_circle"></span>
		</div>
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
			.inner
				display: block
				line-height: 24px
				font-size: 24px
				color: rgb(0, 160, 220)
				transition: all 0.4s linear
				transform: rotate(0)
		.decrease
			transition: all 0.2s linear
			&.move-transition
				opacity: 1
				transform: translate3D(0,0,0)
			&.move-enter-active, &.move-leave-active
				opacity: 0
				transform: translate3D(24px,0,0)
				.inner
					transform: rotate(180deg)
		.count
			width: 12px
			line-height: 24px
			text-align: center
			padding-top: 6px
			font-size: 10px
			color: rgb(147, 153, 159)
</style>
