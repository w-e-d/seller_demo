<template>
    <div class="detail">
        <router-link  replace tag="p" to="/goods">
            返回
        </router-link>
        <h1>商品详情</h1>
    </div>
</template>

<script type="text/ecmascript-6">
export default {
}
</script>

<style lang="stylus">
    .detail
        position: fixed
        z-index: 2
        top: 0
        left: 0
        width: 100%
        height: 100%
        background: #fff
</style>
