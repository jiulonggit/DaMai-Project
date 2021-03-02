<template>
  <div class="home">
    <!-- 头部 -->
    <div class="head">
      <header01></header01>
    </div>
    <!-- 横向导航 -->
    <div class="linenav">
      <linenav :linenavList='linenavList'></linenav>
    </div>
    <!-- 轮播 -->
    <div class="lb">
      <div class="lbcontent">
          <mylb :lbList='lbList'></mylb>
      </div>
      <div class="homenav">
          <myhomenav :homenavlist='homenavList'></myhomenav>
      </div>
    </div>
    <!-- 推荐和开售 -->
    <div class="selltab"> 
      <myselltab :sellList='sellList'></myselltab>
    </div>
    <!-- 楼层 -->
    <div class="floor">
      <myfloor :floorList='floorList' :seniorityList="seniorityList"></myfloor>
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
import mylb from "@/components/lb/lb";
import myhomenav from "@/components/menu/homenav";
import myselltab from "@/components/sell/sell";
import myfloor from "@/components/floor/floor";
import myfooter from "@/components/foot/footer";

export default {
  name: "Home",
  components: {
    header01: header01,
    linenav: linenav,
    mylb:mylb,
    myhomenav:myhomenav,
    myselltab:myselltab,
    myfloor:myfloor,
    myfooter:myfooter
  },
  data(){
    return{
      linenavList:[],
      lbList:[],
      homenavList:[],
      sellList:[],
      floorList:[],
      seniorityList:[]
    }
  },
  methods:{
    getData(){
      this.axios.get('http://127.0.0.1:3721/api/index/lineNav').then(res=>{
        console.log(res.data.data);
        this.linenavList=res.data.data
      })
       this.axios.get('http://127.0.0.1:3721/api/index/carousel').then(res=>{
        console.log(res.data.data);
        this.lbList=res.data.data
      })
      this.axios.get('http://127.0.0.1:3721/api/index/nav').then(res=>{
        console.log(res.data.data);
        this.homenavList=res.data.data
      })
      this.axios.get('http://127.0.0.1:3721/api/index/recommend').then(res=>{
        console.log(res.data.data);
        this.sellList=res.data.data
      })
       this.axios.get('http://127.0.0.1:3721/api/index/floor').then(res=>{
        console.log(res.data.data);
        this.floorList=res.data.data
      })
      this.seniorityList=[];
      for(var i=0;i<5;i++){
        this.axios.get("http://127.0.0.1:3721/api/index/seniority").then(res=>{
          this.seniorityList.push(res.data.data)
        })
      }
    }
  },
  mounted(){
    this.getData();
  }
};
</script>

<style lang="less" scoped>
  .home{
    width: 100%;
    .linenav{
      width:95%;
      margin: 0 auto;
    }
    .lb{
      // width: 100%;
      position: relative;
      .homenav{
        margin: 0 4.9%;
        position: absolute;
        top: 0;
        left: 0;
      }
    }
    .floor{
      margin: 0 5%;
    }
  }
</style>