<template>
  <div class="jcWrap">
    <h4>猜你喜欢</h4>
    <div class="bg"><img src="/static/img/ribbon-totem.png" alt="" /></div>
    <div class="content">
      <div class="big">
        <img :src="foucsList[6].imgUrl" alt="" />
      </div>
      <div class="small">
        <div class="small_item" v-for="index in 6" :key="index">
          <img :src="foucsList[index].imgUrl" alt="" />
        </div>
      </div>
      <div class="big">
        <img :src="foucsList[7].imgUrl" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["foucsList"],
};
</script>

<style lang="less" scoped>
.jcWrap {
  background-color: #fff;
  margin: 20px 5%;
  padding: 10px;
  h4 {
    text-align: center;
    font-size: 16px;
  }
  .bg {
    text-align: center;
    position: relative;
    top: -30px;
    margin-left: 35px;
  }
  .content {
    display: flex;
    .big {
      flex: 2;
      img {
        width: 95%;
      }
    }
    .small {
      flex: 3;
      display: flex;
      flex-wrap: wrap;
      .small_item {
        width: 33.3333%;
        img {
          width: 95%;
        }
      }
    }
  }
}
</style>