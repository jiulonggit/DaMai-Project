<template>
  <div class="header01">
      <!-- 导航 -->
    <div class="top clear">
      <div class="top_left">
        HI,欢迎来到大麦网【
        <router-link to="/login" style="color:red">登录</router-link>&nbsp;&nbsp;
        <router-link to="/register">注册</router-link>】
        <Dropdown>
          <a href="javascript:void(0)">
            我的大麦
            <Icon type="ios-arrow-down"></Icon>
          </a>
          <DropdownMenu slot="list">
            <DropdownItem>驴打滚</DropdownItem>
            <DropdownItem>炸酱面</DropdownItem>
            <DropdownItem disabled>豆汁儿</DropdownItem>
            <DropdownItem>冰糖葫芦</DropdownItem>
            <DropdownItem divided>北京烤鸭</DropdownItem>
          </DropdownMenu>
        </Dropdown>
      </div>
      <ul class="top_right clear">
          <li>大麦网微信</li>
          <li>手机版</li>
          <li><Dropdown>
          <a href="javascript:void(0)">
            客户服务
            <Icon type="ios-arrow-down"></Icon>
          </a>
          <DropdownMenu slot="list">
            <DropdownItem>驴打滚</DropdownItem>
            <DropdownItem>炸酱面</DropdownItem>
            <DropdownItem disabled>豆汁儿</DropdownItem>
            <DropdownItem>冰糖葫芦</DropdownItem>
            <DropdownItem divided>北京烤鸭</DropdownItem>
          </DropdownMenu>
        </Dropdown>
        </li>
          <li><Dropdown>
          <a href="javascript:void(0)">
            网站导航
            <Icon type="ios-arrow-down"></Icon>
          </a>
          <DropdownMenu slot="list">
            <DropdownItem>驴打滚</DropdownItem>
            <DropdownItem>炸酱面</DropdownItem>
            <DropdownItem disabled>豆汁儿</DropdownItem>
            <DropdownItem>冰糖葫芦</DropdownItem>
            <DropdownItem divided>北京烤鸭</DropdownItem>
          </DropdownMenu>
        </Dropdown></li>
          <li>English</li>
      </ul>
    </div>
    <!-- 图标和搜索 -->
    <div class="logo">
        <img src="/static/img/logo.png" alt="">
        <Dropdown>
          <a href="javascript:void(0)">
            北京
            <Icon type="ios-arrow-down"></Icon>
          </a>
          <DropdownMenu slot="list">
            <DropdownItem>上海</DropdownItem>
            <DropdownItem>广东</DropdownItem>
            <DropdownItem>深圳</DropdownItem>
            <DropdownItem>香港</DropdownItem>
            <DropdownItem>南京</DropdownItem>
          </DropdownMenu>
        </Dropdown>
        <div class="search">
            <Input search enter-button="搜索" placeholder="请输入要搜索的内容..." />
        </div>
        
    </div>
  </div>
</template>

<style lang="less" scoped>
    .header01{
        // border-bottom: 1px solid rgb(189, 188, 188);
        line-height: 30px;
        padding: 0 5%;
        padding-bottom: 5%;
        a{
            color: #666;
        }
        .top{
             border-bottom: 1px solid rgb(221, 221, 221);
            .top_left{
                float: left;
            }
            .top_right{
                float:right;
                li{
                    float: left;
                    margin: 0 10px;
                }
            }
        }
        .logo{
            margin-top: 20px;
            img{
                float:left;
            }
            .search{
                width:40%;
                margin: -20px auto;
            }
        }
    }
</style>