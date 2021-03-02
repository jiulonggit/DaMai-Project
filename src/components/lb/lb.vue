<template>
    <Carousel autoplay  loop class="lb">
        <CarouselItem v-for="(item,index) in lbList" :key="index">
            <div class="demo-carousel">
                <img :src="item.imgUrl" alt="">
            </div>
        </CarouselItem>
       
    </Carousel>
</template>
<script>
    export default {
        props:['lbList'],
        data () {
            return {
                value2: 0
            }
        }
    }
</script>
<style lang="less" scoped>
    .lb{
       img{
           width: 100%;
       }
    }
</style>