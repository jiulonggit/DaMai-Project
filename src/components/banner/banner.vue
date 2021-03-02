<template>
    <div class="bannerWrap">
        <div class="b" v-for="(item,index) in bannerList" :key="index">
            <img :src="item.imgUrl" alt="">
        </div>
    </div>
</template>

<script>
export default {
    props:['bannerList']
}
</script>
<style lang="less" scoped>
    .bannerWrap {
        margin:20px 5%;
        display: flex;
        .b {
            flex:1;
            img {
                width: 90%;
            }
        }
    }
</style>