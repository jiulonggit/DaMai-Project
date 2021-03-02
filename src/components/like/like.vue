<template>
    <div class="likeWrap">
        <h4>猜你喜欢</h4>
        <div class="bg"><img src="/static/img/ribbon-totem.png" alt=""></div>
        <ul>
            <li v-for="(item,index) in likeList" :key="index">
                <p><img :src="item.imgUrl" alt=""></p>
                <p>{{item.itemName}}</p>
                <p>票价：￥{{item.minPrice}}起</p>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:['likeList']
}
</script>

<style lang="less" scoped>
    .likeWrap{
        background-color: #fff;
        padding: 10px;
        margin: 20px 5%;
        h4{
            text-align: center;
            font-size: 16px;
        }
        .bg{
            text-align: center;
            position: relative;
            top: -30px;
            margin-left: 35px;
        }
        ul{
            display: flex;
            li{
                flex: 1;
                padding: 10px;
                img{
                    width: 90%;
                }
            }
        }
    }
</style>