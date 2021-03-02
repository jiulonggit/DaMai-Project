<template>
  <div class="listWrap">
    <header01></header01>
    <div class="title">共<span>23</span>个商品</div>
    <div class="list">
      <div class="list_left">
        <div class="query">
          <querycity :cityList="cityList"></querycity>
          <querysort :sortList="sortList"></querysort>
          <querytime></querytime>
        </div>
        <div class="query_list">
          <Tabs value="name1">
            <TabPane label="热门推荐" name="name1">
                <dl v-for="(item,index) in tabList.rows" :key="index">
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <h4>[{{item.areaName}}] {{item.itemName}}</h4>
                        <p>{{item.abstractMessage}}</p>
                        <p><Icon type="ios-apps" color="red" />{{item.startTime}}</p>
                        <p><Icon type="ios-pin" color="red" /> {{item.adress}}</p>
                        <p>{{item.minPrice}}-{{item.maxPrice}}<span>售票中</span></p>
                        <p><Icon type="md-qr-scanner" color="red"/> 电子票</p>
                    </dd>
                </dl>
                <p style="text-align:center"><Page :total="25" /></p>
            </TabPane>
            <TabPane label="最近开场" name="name2">
                <dl v-for="(item,index) in tabList.rows" :key="index">
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <h4>[{{item.areaName}}] {{item.itemName}}</h4>
                        <p>{{item.abstractMessage}}</p>
                        <p><Icon type="ios-apps" color="red" />{{item.startTime}}</p>
                        <p><Icon type="ios-pin" color="red" /> {{item.adress}}</p>
                        <p>{{item.minPrice}}-{{item.maxPrice}}<span>售票中</span></p>
                        <p><Icon type="md-qr-scanner" color="red"/> 电子票</p>
                    </dd>
                </dl>
                <p style="text-align:center"><Page :total="25" /></p>
            </TabPane>
            <TabPane label="最新上架" name="name3">
                <dl v-for="(item,index) in tabList.rows" :key="index">
                    <dt><img :src="item.imgUrl" alt=""></dt>
                    <dd>
                        <h4>[{{item.areaName}}] {{item.itemName}}</h4>
                        <p>{{item.abstractMessage}}</p>
                        <p><Icon type="ios-apps" color="red" />{{item.startTime}}</p>
                        <p><Icon type="ios-pin" color="red" /> {{item.adress}}</p>
                        <p>{{item.minPrice}}-{{item.maxPrice}}<span>售票中</span></p>
                        <p><Icon type="md-qr-scanner" color="red"/> 电子票</p>
                    </dd>
                </dl>
                <p style="text-align:center"><Page :total="25" /></p>
            </TabPane>
          </Tabs>
        </div>
      </div>

      <div class="list_right">
          <h3>您还可能喜欢</h3>
          <div class="like">
              <dl v-for="(item,index) in likeList" :key="index">
                  <dt><img :src="item.imgUrl" alt=""></dt>
                  <dd>
                       <h4>{{item.itemName}}</h4>
                        <p>{{item.address}}</p>
                        <p>{{item.startDate}}-{{item.endDate}}</p>
                        <p>￥{{item.minPrice}}起</p>
                  </dd>
              </dl>
          </div>
      </div>
    </div>
    <foot></foot>
  </div>
</template>

<script>
import header01 from "@/components/header/header01";
import foot from "@/components/foot/footer";
import querycity from "@/components/query/querycity";
import querysort from "@/components/query/querysort";
import querytime from "@/components/query/querytime";
export default {
  data() {
    return {
      cityList: [],
      sortList: [],
      tabList:[],
      likeList:[]
    };
  },
  components: {
    header01: header01,
    foot: foot,
    querycity: querycity,
    querysort: querysort,
    querytime: querytime,
  },
  methods: {
    getData() {
      this.axios.get("http://127.0.0.1:3721/api/list/querycity").then((res) => {
        this.cityList = res.data.data;
      });
      this.axios.get("http://127.0.0.1:3721/api/list/sortgoods").then((res) => {
        this.sortList = res.data.data;
      });
      this.axios.get("http://127.0.0.1:3721/api/list/querygoodsinfos").then((res) => {
        this.tabList = res.data.data;
        console.log(this.tabList);
      });
      this.axios.get("http://127.0.0.1:3721/api/list/guesslike").then((res) => {
        this.likeList = res.data.data;
      });
    },
  },
  mounted() {
    this.getData();
  },
};
</script>

<style lang="less" scoped>
.listWrap {
    margin:0 5%;
  .title {
    line-height: 40px;
    padding-left: 100px;
    background-color: #fff;
    border-bottom: 1px solid #efefef;
    // width: 88%;
    // margin: 0 5.5%;
    span {
      color: #f60;
    }
  }
  .list {
   padding: 10px;
//    margin: -10px 5%;
    display: flex;
    .list_left{
        flex: 4;
        margin-right: 20px;
        .query{
            background-color: #fff;
            margin-bottom: 20px;
        }
        .query_list{
            background-color: #fff;
           
            dl{
                margin-bottom: 25px;
                 padding-left: 20px;
                dt{
                    float: left;
                    width: 120px;
                    
                    img{
                        width: 100%;
                    }
                    margin-right: 10px;
                }
                dd{
                   
                    line-height: 25px;
                }
            }
        }
    }
    .list_right{
        flex: 1;
        background-color: #fff;
        h3{
            background-color: #CCC;
            line-height: 30px;
            padding-left: 10px;
        }
        .like{
            padding: 10px;
            dl{
                display: flex;
                dt{
                    flex: 4;
                    img{
                        width: 90%;
                    }
                }
                dd{
                    flex: 5;
                    h4{
                        margin-bottom: 20px;
                    }
                }
            }
        }
    }
  }
}
</style>