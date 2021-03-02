<template>
  <div class="multipage">
    <!-- 头部 -->
    <div class="head">
      <header01></header01>
    </div>
    <!-- 横向导航 -->
    <div class="linenav">
      <linenav :linenavList="linenavList"></linenav>
    </div>
    <!-- 轮播 -->
    <div class="lb">
      <mylb :lbList="lbList"></mylb>
    </div>
    <!-- 猜你喜欢 -->
    <div class="like">
      <youlike :likeList="likeList"></youlike>
    </div>
    <!-- 精彩聚焦 -->
    <div class="foucs">
      <myfoucs :foucsList="foucsList"></myfoucs>
    </div>
    <!-- 3张插图 -->
    <div class="banner">
      <mybanner :bannerList="bannerList"></mybanner>
    </div>
    <!-- 分类查询 -->
    <div class="category">
      <mycategory :cataList="categoryList"></mycategory>
    </div>
    <!-- 热门排行 -->
    <div class="hot">
      <myhot :hotList="hotList"></myhot>
    </div>
    <!-- 日历 -->
    <div class="data">
      <mydata></mydata>
    </div>
    <!-- 合作 -->
    <div class="hz">
      <h4>合作方</h4>
      <div class="bg"></div>
      <div class="hzList">
        <div class="item" v-for="(item, index) in hzList" :key="index">
          <img :src="'/static/img/' + item" alt="" />
        </div>
      </div>
    </div>
    <!-- 尾部 -->
    <div class="foot">
      <myfooter></myfooter>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import header01 from "@/components/header/header01";
import linenav from "@/components/menu/linenav";
import myfooter from "@/components/foot/footer";
import mylb from "@/components/lb/lb";
import youlike from "@/components/like/like";
import myfoucs from "@/components/jcjj/jc";
import mybanner from "@/components/banner/banner";
import mycategory from "@/components/category/category";
import myhot from "@/components/hot/hot";
import mydata from "@/components/dmCalendar/data";

export default {
  name: "Home",

  components: {
    header01: header01,
    linenav: linenav,
    myfooter: myfooter,
    mylb: mylb,
    youlike: youlike,
    myfoucs: myfoucs,
    mybanner: mybanner,
    mycategory: mycategory,
    myhot: myhot,
    mydata: mydata,
  },
  data() {
    return {
      linenavList: [],
      likeList: [],
      foucsList: [],
      bannerList: [],
      categoryList: [],
      hotList: [],
      hzList: [
        "hz1.png",
        "hz2.png",
        "hz4.png",
        "hz5.png",
        "hz6.png",
        "hz7.png",
        "hz3.png",
        "hz8.png",
        "hz9.png",
        "hz10.png",
        "hz11.png",
        "hz12.png",
      ],
    };
  },
  methods: {
    getData() {
      this.axios.get("http://127.0.0.1:3721/api/index/lineNav").then((res) => {
        // console.log(res.data.data);
        this.linenavList = res.data.data;
      });
      this.axios.get("http://127.0.0.1:3721/api/index/carousel").then((res) => {
        // console.log(res.data.data);
        this.lbList = res.data.data;
      });
      this.axios
        .get("http://127.0.0.1:3721/api/multiple/getGuessYouLike")
        .then((res) => {
          // console.log(res.data.data);
          this.likeList = res.data.data;
        });
      this.axios
        .get("http://127.0.0.1:3721/api/multiple/getWonderfulData")
        .then((res) => {
          // console.log(res.data.data);
          this.foucsList = res.data.data;
        });
      this.axios
        .get("http://127.0.0.1:3721/api/multiple/getAdimgUrl")
        .then((res) => {
          // console.log(res.data.data);
          this.bannerList = res.data.data;
        });
      this.axios
        .get("http://127.0.0.1:3721/api/multiple/getParentChild")
        .then((res) => {
          // console.log(res.data.data);
          this.categoryList = res.data.data;
        });
      this.axios
        .get("http://127.0.0.1:3721/api/multiple/getPopularSearch")
        .then((res) => {
          // console.log(res.data.data);
          this.hotList = res.data.data;
        });
    },
  },
  mounted() {
    this.getData();
  },
};
</script>

<style lang="less" scoped>
.multipage {
  .linenav {
    width: 95%;
    margin: 0 auto;
  }
  .data {
    margin: 20px 5%;
  }
  .hz {
    h4 {
      font-size: 16px;
      text-align: center;
      line-height: 50px;
    }
    .bg {
      width: 100%;
      height: 60px;
      background: url(/static/img/ribbon-totem.png) center 0 no-repeat;
      margin-top: -40px;
      margin-left: 15px;
    }
    .hzList {
      padding: 20px 200px;
      display: flex;
      flex-wrap: wrap;
      .item {
        padding: 20px;
        width: 16.666667%;
        img {
          width: 70%;
        }
      }
    }
  }
}
</style>