<template>
    <Tabs value="name1" class="selltab">
        <TabPane label="今日推荐" name="name1">
            <div class="a">
                <div class="sellcontent" v-for="(item,index) in sellList" :key="index">
                    <p><img :src="item.imgUrl" alt=""></p>
                    <p class="title">{{item.itemName}}</p>
                    <p>票价：￥{{item.minPrice}}起</p>
                </div>
            </div>
            
        </TabPane>
        <TabPane label="即将开售" name="name2">
            <div class="b">
                <div class="sellcontent" v-for="(item,index) in sellList" :key="index">
                    <p><img :src="item.imgUrl" alt=""></p>
                    <p class="title">{{item.itemName}}</p>
                    <p>票价：￥{{item.minPrice}}起</p>
                </div>
            </div>
        </TabPane>
    </Tabs>
</template>
<script>
export default {
    props:['sellList']
}
</script>

<style lang="less" scoped>
    .selltab{
        margin:1% 5%;
        background-color: #fff;
        .a,.b{
            display: flex;
            .sellcontent{
                flex: 1;
                margin-left:20px;
                img{
                    width: 70%;
                }
            }
            .title{
                font-weight: bolder;
                    width: 160px;
                    white-space: nowrap;
                    overflow: hidden;
                    text-overflow: ellipsis;
            }
        }
    }
</style>