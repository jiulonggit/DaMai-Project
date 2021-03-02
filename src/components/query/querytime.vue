<template>
  <div class="querytimeWrap">
    <ul>
      <li>时间 :</li>
      <li class="all">全部</li>
      <li>今天</li>
      <li>明天</li>
      <li class="w150"><DatePicker type="date" placeholder="选择日期" style="width: 200px"></DatePicker></li>-
      <li class="w150"><DatePicker type="date"  placeholder="选择日期" style="width: 200px"></DatePicker></li>
    </ul>
  </div>
</template>

<style lang="less" scoped>
    .querytimeWrap{
        padding: 20px;
        background-color: #fff;
        ul{
            border-bottom: 1px solid #d8d8d8;
            display: flex;
            padding-bottom: 30px;
            padding-left: 100px;
            li{
                font-size: 16px;
                width: 80px;
                text-align: center;
               
            }
             .w150{
                    width: 210px;
                }
            .all{
                background-color: red;
                color: white;
            }
        }
    }
</style>