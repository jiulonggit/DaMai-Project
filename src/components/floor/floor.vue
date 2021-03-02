<template>
  <div class="floorWrap">
    <div class="floor" v-for="(item, index) in floorList" :key="index">
      <div class="f_left">
        <h4>{{ index + 1 }}F{{ item.itemTypeName }}</h4>
        <div class="floorItem">
          <div class="big">
            <img :src="item.items[0].imgUrl" alt />
          </div>
          <div class="small">
            <dl v-for="(item2, index2) in item.items" :key="index2" v-if="index2 > 0">
            
              <dt>
                <img :src="item2.imgUrl" alt />
              </dt>
              <dd>
                <p>{{ item2.itemName }}</p>
                <p>{{ item2.startDate }}-{{ item2.endDate }}</p>
                <p>{{ item2.address }}</p>
                <p>￥{{ item2.minPrice }}起</p>
              </dd>
            </dl>
          </div>
        </div>
      </div>
      <div class="f_right">
        <h3>查看全部</h3>
        <p>热门演出排行</p>
        <ul>
          <li v-for="(item2, index2) in seniorityList[index]" :key="index2">
            <span>{{ index2 + 1 }}</span>
            {{ item2.itemName }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["floorList", "seniorityList"],
};
</script>

<style lang="less" scoped>
.floorWrap {
  width: 100%;
  .floor {
    display: flex;
    margin-bottom: 20px;
    .f_left {
      flex: 3;
      margin-right: 0px;
      background-color: #fff;
      padding: 20px;
      .floorItem {
        display: flex;
        .big {
          flex: 1;
          img {
            width: 90%;
          }
        }
        .small {
          flex: 2;
          display: flex;
          flex-wrap: wrap;
          dl {
            width: 50%;
            display: flex;
            dt {
              flex: 4;
              img {
                width: 90%;
              }
            }
            dd {
              flex: 5;
              h3 {
                width: 140px;
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
                margin-bottom: 70px;
              }
            }
          }
        }
      }
    }

    .f_right {
      margin-left: 1%;
      flex: 1;
      background-color: #fff;
      padding: 20px;
      line-height: 30px;
      h3 {
        text-align: right;
      }
      ul {
        li {
          line-height: 28px;
          span {
            display: inline-block;
            width: 20px;
            height: 16px;
            line-height: 20px;
            text-align: center;
            background-color: #aaa;
            color: #fff;
            margin-right: 10px;
          }
          .red {
            background-color: #f40;
          }
        }
      }
    }
  }
}
</style>