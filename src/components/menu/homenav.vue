<template>
  <div class="homenav">
    <ul>
      <li v-for="(item,index) in homenavlist" :key="index">
        <img :src="item.icon" alt />
        {{item.itemType}}
        <div>
          <p v-for="(item2,index2) in item.children" :key="index2">
            <router-link to="/list">{{item2.itemType}}</router-link>
            </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["homenavlist"],
};
</script>>

<style lang="less" scoped>
.homenav {
  width: 200px;
  background-color: red;
  li {
    line-height: 40px;
    margin: 20px 0;
    padding-left: 20px;
    color: white;
    transition: all 0.5s;
    background: url(/static/img/jiantou.png) 180px center no-repeat;
    position: relative;
    cursor: default;
    img {
      vertical-align: middle;
      width: 20px;
      margin-right: 20px;
    }
    div {
      position: absolute;
      top: 0;
      left: 200px;
      width: 400px;
      background-color: rgba(0, 0, 0, 0.3);
      color: red;
      padding: 30px;
      line-height: 40px;
      display: none;
    }
  }
  li:last-child {
    margin-bottom: 0;
  }
  li:hover {
    background-color: red;
    padding-left: 50px;
  }
  li:hover div {
    display: block;
  }
}
</style>