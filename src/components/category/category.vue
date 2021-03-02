<template>
  <div class="categroyWrap">
    <Tabs value="name1">
      <TabPane label="音乐专区" name="name1">
        <ul>
            <li v-for="(item,index) in cataList" :key="index">
                <dl>
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <p class="title">{{item.itemName}}</p>
                        <p>{{item.startDate}}-{{item.endDate}}</p>
                        <p>{{item.address}}</p>
                        <p>￥{{item.minPrice}}起</p>
                    </dd>
                </dl>
            </li>
        </ul>
      </TabPane>
      <TabPane label="舞蹈专区" name="name2">
        <ul>
            <li v-for="(item,index) in cataList" :key="index">
                <dl>
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <p class="title">{{item.itemName}}</p>
                        <p>{{item.startDate}}-{{item.endDate}}</p>
                        <p>{{item.address}}</p>
                        <p>￥{{item.minPrice}}起</p>
                    </dd>
                </dl>
            </li>
        </ul>
      </TabPane>
    </Tabs>
  </div>
</template>

<script>
export default {
    props:['cataList']
}
</script>

<style lang="less" scoped>
    .categroyWrap{
        margin: 20px 5%;
        padding: 10px;
        background-color: #fff;
        ul{
            display: flex;
            flex-wrap: wrap;
            li{
                width: 33.33333%;
                dl{
                    display: flex;
                    dt{
                        flex: 2;
                        img{
                            width: 90%;
                        }
                    }
                    dd{
                        flex: 3;
                        .title{
                            color: black;
                            font-weight: bold;
                        }
                    }
                }
            }

        }
    }
</style>