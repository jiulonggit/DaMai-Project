<template>
    <div class="linenav clear">
        <h4 v-show="getId==0">全部商品分类</h4>
        <ul class="clear">
            <li v-show="getId!=0"><router-link to="/">首页</router-link></li>
            <li v-for="(item,index) in linenavList" :key="index" :class="{active:item.id==getId}">
                <router-link :to="'/mp:'+item.id">{{item.aliasName}}</router-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    props:['linenavList'],
    computed:{
        getId(){
            if(this.$route.params.id){
                return this.$route.params.id
            }else{
                return 0
            }
        }
    }
}
</script>

<style lang="less" scoped>
    .linenav{
        line-height: 40px;
        width: 100%;
        display: flex;
        h4{
            width: 200px;
            background-color: black;
            color: #fff;
            text-align: center;
            float: left;
        }
        ul{
            flex: 1;

            background-color: #fff;
            li{
                float: left;
                a{
                     padding: 0 20px;
                     display: block;
                      font-size: 16px;
                      color: grey;
                }
               
            }
            li:hover{
                background-color:#f60;
            }
            li:hover a{
                color: white;
            }
            li.active{
               background-color:red;
               a{
                   color: red;
               }
           }
        }
    }
</style>