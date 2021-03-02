<template>
    <div class="querycityWrap">
        <ul>
            <li>城市 :</li>
            <li class="all">全部</li>
            <li v-for="(item,index) in cityList" :key="index">
                {{item.name}}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:['cityList']
}
</script>

<style lang="less" scoped>
    .querycityWrap{
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
            .all{
                background-color: red;
                color: white;
            }
        }
    }
</style>