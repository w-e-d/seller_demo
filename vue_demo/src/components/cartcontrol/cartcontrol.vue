<template>
	<div class="cartcontrol">
		<div v-show="food.count>0" class="decrease icon-remove_circle_outline"></div>
		<div v-show="food.count>0" class="count"></div>
		<div @click="addCart" class="add icon-add_circle"></div>
	</div>
</template>

<script>
	export default{
		data() {
			return {
				
			}
		},

		methods: {
			addCart() {
				console.log(111)
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
</style>