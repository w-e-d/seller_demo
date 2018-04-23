<template>
	<div class="goods">
		<div class="menu-wrapper">
      
	    </div>
	    <div class="foods-wrapper">
	    	
	    </div>
	</div>
</template>

<script type="text/ecmascript-6">
	import axios from 'axios';

	const ERR_OK = 0;

	export default {
		props:{
			seller:{
				type: Object
			}
		},
		data() {
			return {
				goods: []
			}
		},
		created() {
			axios.get('/api/goods').then((res) => {
				if(res.data.errno === ERR_OK){
					this.goods = res.data.data;
				}
			})
		}
	};
</script>

<style lang="stylus" rel="stylesheet/stylus">
	.goods
		display: flex
		position: absolute
		top: 176px
		bottom: 46px
		width: 100%
		overflow: hidden
		.menu-wrapper
			flex: 0 0 80px
			width: 80px
			background: #f3f5f7
		.foods-wrapper
			flex: 1
</style>	