<template>
	<div class="header">
    	<div class="content-wrapper">
    		<div class="avatar">
    			<img width="64" height="64" :src="seller.avatar">
    		</div>
    		<div class="content">
    			<div class="title">
    				<span class="brand"></span>
    				<span class="name">{{seller.name}}</span>
    			</div>
    			<div class="description">
    				{{seller.description}}/{{seller.deliveryTime}}分钟送达
    			</div>
    			<div v-if="seller.supports" class="support">
    				<span class="icon" :class="classMap[seller.supports[0].type]"></span>
    				<span class="text">{{seller.supports[0].description}}</span>
    			</div>
    		</div>
    		<div v-if="seller.supports" class="support-count" @click="showDetail">
    			<span class="count">{{seller.supports.length}}个</span>
    			<i class="icon-keyboard_arrow_right"></i>
    		</div>
    	</div>
    	<div class="bulletin-wrapper" @click="showDetail">
    			<span class="bulletin-title"></span>
    			<span class="bulletin-text">{{seller.bulletin}}</span>
    			<i class="icon-keyboard_arrow_right"></i>
    	</div>
    	<div class="background">
    		<img :src="seller.avatar" width="100%" height="100%">
    	</div>
    	<div v-show="detailShow" class="detail">
    		<div class="detail-wrapper  clearfix">
    			<div class="detail-main">

    			</div>
    		</div>
    		<div class="detail-close" @click="hiddenDetail">
    				<i class="icon-close"></i>
    		</div>
    		
    	</div>
    </div>
</template>

<script type="text/ecmascript-6">
	export default {
		props:{
			seller:{
				type:Object
			}
		},
		data() {
			return {
				detailShow:false
			};
		},
		methods:{
			showDetail() {
				this.detailShow = true;
			},
			hiddenDetail() {
				this.detailShow = false
			}
		},
		created() {
			this.classMap = ['decrease','discount','special','invoice','guarantee'];
		}
	};
</script>

<style lang="stylus" rel="stylesheet/stylus">
	@import "../../common/stylus/mixin.styl"
	@import "../../common/stylus/base.styl"

	.header
		position:relative
		overflow:hidden
		color:#fff
		font-size:14px
		background:rgba(7,17,27,0.5)
		.content-wrapper
			position:relative
			display:flex
			padding:24px 12px 18px 24px
			.avatar,img
				border-radius:2px
			.content
				margin-left:16px
				.title
					display:flex
					margin:2px 0 8px 0
					.brand
						display:block
						width:30px
						height:18px
						bg-image('brand')
						background-size:contain
					.name
						margin-left:6px
						font-size:16px
						line-height:18px
						font-weight:bold
				.description
					margin-bottom:10px
					line-height:12px
					font-size:12px
				.support
					display:flex
					.icon
						display:block
						width:12px
						height:12px
						margin-right:4px
						background-size:contain
						background-repeat:no-repeat
						&.decrease
							bg-image('decrease_1')
						&.discount
							bg-image('discount_1')
						&.guarantee
							bg-image('guarantee_1')
						&.invoice
							bg-image('invoice_1')
						&.special
							bg-image('special_1')
					.text
						line-height:12px
						font-size:10px
			.support-count
				position:absolute
				right:12px
				bottom:18px
				padding:0 8px
				height:24px
				line-height:24px
				border-radius:14px
				background:rgba(0,0,0,0.2)
				text-align:center
				font-size:0
				.count
					vertical-align:top
					font-size:10px
				.icon-keyboard_arrow_right
					margin-left:2px
					line-height:24px
					font-size:12px
		
		.bulletin-wrapper
			position:relative
			display:flex
			align-items:center
			height:28px
			line-height:28px
			padding:0 22px 0 12px
			background:rgba(7,17,27,0.2)
			.bulletin-title
				display:block
				width:22px
				height:12px
				bg-image:('bulletin')
				background-size:cover
			.bulletin-text
				display:block
				width:calc(100% - 22px)
				white-space:nowrap
				overflow:hidden
				text-overflow:ellipsis
				margin:0 4px
				font-size:10px
			.icon-keyboard_arrow_right
				position:absolute
				font-size:10px
				right:12px
				top:8px
		
		.background
			position:absolute
			top:0
			left:0
			width:100%
			height:100%
			z-index:-1
			filter:blur(10px)		
		.detail
			position:fixed
			top:0
			left:0
			z-index:100
			width:100%
			height:100%
			overflow:auto
			background:rgba(7,17,27,0.8)
			.detail-wrapper
				min-height:100%
				.detail-main
					margin-top:64px
					padding-bottom:64px
			.detail-close
					position:relative
					width:32px
					height:32px
					margin:-64px auto 0 auto
					clear:both
					font-size:32px
					

</style>		