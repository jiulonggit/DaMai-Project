<template>
    <div class="hotWrap">
        <h4>热门排行</h4>
        <div class="bg"><img src="/static/img/ribbon-totem.png" alt=""></div>
        <div class="content">
            <div class="big">
                <img :src="hotList[0].imgUrl" alt="">
            </div>
            <div class="small">
                <dl v-for="(item,index) in hotList" :key="index" v-if="index>0">
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <p class="title">{{item.itemName}}</p>
                            <p class="font">{{item.startDate}}-{{item.endDate}}</p>
                            <p class="font">{{item.address}}</p>
                            <p class="font">￥{{item.minPrice}}起</p>
                    </dd>
                </dl>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['hotList']
}
</script>

<style lang="less" scoped>
    .hotWrap{
        background-color: #fff;
        margin: 20px 5%;
        padding: 10px;
        h4{
            font-size: 16px;
            text-align: center;
        }
        .bg{
            text-align: center;
            position: relative;
            top: -30px;
            margin-left: 30px;
        }
        .content{
            display: flex;
            .big{
                flex: 1;
                img{
                    width: 95%;
                    height: 100%;
                }
            }
            .small{
                flex: 4;
                display: flex;
                flex-wrap: wrap;
                dl{
                    width: 33.33333%;
                    display: flex;
                    dt{
                        flex: 3;
                        img{
                            width: 95%;
                            height: 250px;
                        }
                    }
                    dd{
                        flex: 4;
                        .title{
                            font-weight: bold;
                            color: black;
                            margin-bottom: 70px;
                        }
                       
                    }
                }
            }
        }
    }
</style>