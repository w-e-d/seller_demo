<template>
  <div>
    <v-header :seller="seller"></v-header>
    <div class="tab border-1px">
      <div class="tab-item">
        <router-link replace tag="li" to="/goods">
          商品
        </router-link>
      </div>
      <div class="tab-item">
        <router-link replace tag="li" to="/ratings">
          评论
        </router-link> 
      </div>
      <div class="tab-item">
        <router-link replace tag="li" to="/seller">
          商家
        </router-link> 
      </div>
    </div>
    <router-view class="main-content" :seller="seller"></router-view>
  </div>
</template>

<script type="text/ecmascript-6">
  import header from './components/header/header.vue';
  import axios from 'axios';

  const ERR_OK = 0;

  export default {
    data() {
      return {
        seller:{}
      }
    },

    created() {
      axios.get('/api/seller').then((response)=>{
        if(response.data.errno == 0){
          this.seller = response.data.data;
        }
      })
    },

    components:{
      'v-header':header
    }
  }

</script>
    
<style lang="stylus" rel="stylesheet/stylus">
  @import "./common/stylus/mixin.styl"

    .tab
      display:flex
      width:100%
      height:40px
      line-height:40px
      border-1px(rgba(7,17,27,0.1))

      .tab-item
        flex:1
        text-align:center
        &>a
          display:block
          font-size:14px
          color:rgb(77,85,93)
          &.active
            color:rgb(240,20,20)
            font-weight:bold
</style>
