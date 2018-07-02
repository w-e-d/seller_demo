<template>
	<div class="shopcart">
		<div class="content">
			<div class="content-left">
				<div class="logo-wrapper">
					<div class="logo">
						<span class="icon-shopping_cart"></span>
					</div>
				</div>
				<div class="price">￥48</div>
				<div class="desc">另需配送费2元</div>
			</div>
			<div class="content-right">
				<div class="pay">￥12元</div>
			</div>
		</div>
	</div>
</template>

<script type="text/ecmascript-6">
	export default{};
</script>

<style lang="stylus">
	.shopcart
		position: fixed
		left: 0
		bottom: 0
		z-index: 50
		width: 100%
		height: 48px
		background: #000
		.content
			display: flex
			background: #141d27
			font-size: 0
			.content-left
				flex: 1
				.logo-wrapper
					display: inline-block
					position: relative
					top: -10px
					margin: 0 12px
					padding: 6px
					width: 56px
					height: 56px
					box-sizing: border-box
					vertical-align: top
					border-radius: 50%
					background: #141d27
					.logo
						width: 100%
						height: 100%
						border-radius: 50%
						text-align: center
						background: #2b343c
						.icon-shopping_cart
							line-height: 44px
							font-size: 24px
							color: #80858a
				.price
					display: inline-block
					line-height: 24px
					margin: 12px 0
					padding-right: 12px
					box-sizing: border-box
					border-right: 1px solid rgba(255,255,255,.1)
					font-size: 16px
					color: #3688ff
					font-weight: 700
				.desc
					display: inline-block
					line-height: 24px
					vertical-align: top
					margin: 12px 0 0 12px
					color: rgba(255,255,255,.4)
					font-size: 10px
			.content-right
				flex: 0 0 105px
				width: 105px
				.pay
					height: 48px
					line-height: 48px
					text-align: center
					font-size:12px
					color: rgba(255,255,255,0.4)
					font-weight: 700
					background: #2b333b
</style>