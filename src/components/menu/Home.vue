<template>
  <div class="home">
    <!-- 头部区域 -->
    <div class="header">
      <header01></header01>
    </div>
    <!-- 横向导航 -->
    <div class="linenav">
      <linenav :linenavList="linenavList"></linenav>
    </div>
    <!-- 轮播和纵向导航 -->
    <div class="navCarousel">
      <mycarousel :carouselList="carouselList"></mycarousel>
      <div class="homenav">
        <homenav :homenavList="homenavList"></homenav>
      </div>
    </div>
    <!-- 推荐和开售 -->
    <div class="home_sell">
      <sell :recommendList="recommendList" :sellList="sellList"></sell>
    </div>
    <!-- 楼层 -->
    <div class="floor">
      <floor :floorList="floorList" :seniorityList="seniorityList"></floor>
    </div>
  </div>
</template>

<script>
import header01 from '@/components/header/header01'
import linenav from '@/components/menu/linenav'
import homenav from '@/components/menu/homenav'
import mycarousel from '@/components/carousel'
import sell from '@/components/sell'
import floor from '@/components/floor'
export default {
  name: 'Home',
  data(){
    return {
      linenavList:[],
      carouselList:[],
      homenavList:[],
      recommendList:[],
      sellList:[],
      floorList:[],
      seniorityList:[]
    }
  },
  components: {
    header01:header01,
    linenav:linenav,
    mycarousel:mycarousel,
    homenav:homenav,
    sell:sell,
    floor:floor
  },
  methods: {
    getData(){
      this.axios.get("http://127.0.0.1:3721/api/index/lineNav").then(res=>{
        this.linenavList=res.data.data
      })
      this.axios.get("http://127.0.0.1:3721/api/index/carousel").then(res=>{
        this.carouselList=res.data.data
      })
      this.axios.get("http://127.0.0.1:3721/api/index/nav").then(res=>{
        this.homenavList=res.data.data
        console.log(this.homenavList)
      })
      this.axios.get("http://127.0.0.1:3721/api/index/recommend").then(res=>{
        this.recommendList=res.data.data
      })
      this.axios.get("http://127.0.0.1:3721/api/index/sell").then(res=>{
        this.sellList=res.data.data
      })
      this.axios.get("http://127.0.0.1:3721/api/index/floor").then(res=>{
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
  mounted() {
    this.getData();
  },
}
</script>
<style lang="less" scoped>
  .home {
    width: 100%;
    .linenav {
      width: 100%;
    }
    .navCarousel {
      position: relative;
      .homenav {
        position: absolute;
        top:0;
        left: 0;
      }
    }
  }
</style>