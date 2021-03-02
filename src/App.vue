<template>
  <div id="app">
    
    <router-view/>
  </div>
</template>


<style lang="less">
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  li{
    list-style-type: none;
  }
  a{
    text-decoration: none;
    color: #666;
  }
  .clear:after{
    content: '';
    display: block;
    clear: both;
  }
  #app{
    background-color: #efefef
  }
</style>
