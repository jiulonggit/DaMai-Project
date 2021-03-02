<template>
  <div class="footerWrap">
    <div class="f1">
      <Row>
        <Col span="3">
          <h3>订购方式</h3>
          <p>在线订购</p>
          <p>上门订购</p>
          <p>电话订购</p>
          <p>大客户团体</p>
        </Col>
        <Col span="3">
          <h3>配送方式</h3>
          <p>在线订购</p>
          <p>上门订购</p>
          <p>电话订购</p>
          <p>大客户团体</p>
        </Col>
        <Col span="3">
          <h3>支付方式</h3>
          <p>在线订购</p>
          <p>上门订购</p>
        </Col>
        <Col span="3">
          <h3>大麦微信</h3>
          <p>
            <img src="static/img/p_code.jpg" alt />
          </p>
        </Col>
        <Col span="3">
          <h3>大麦网触屏版</h3>
          <p>
            <img src="static/img/p_code.jpg" alt />
          </p>
        </Col>
        <Col span="3">
          <h3>账户安全</h3>
          <p>在线订购</p>
          <p>上门订购</p>
          <p>电话订购</p>
          <p>大客户团体</p>
        </Col>
        <Col span="3">
          <h3>配送方式</h3>
          <p>在线订购</p>
          <p>上门订购</p>
          <p>电话订购</p>
          <p>大客户团体</p>
        </Col>
        <Col span="3">
          <h3>特色服务</h3>
          <p>在线订购</p>
        </Col>
      </Row>
    </div>
    <div class="foot">
      <Row type="flex" justify="center">
        <Col span="1">公司介绍</Col>
        <Col span="1">品牌识别</Col>
        <Col span="1">企业荣誉</Col>
        <Col span="1">隐私声明</Col>
        <Col span="1">联系及合作</Col>
        <Col span="1">招聘信息</Col>
        <Col span="1">网站地图</Col>
        <Col span="1">友情链接</Col>
        <Col span="1">公司大事记</Col>
      </Row>
      <ul class="footpic">
        <li>
          <img src="static/img/piao.png" alt />
        </li>
        <li>
          <img src="static/img/dzyy.png" alt />
        </li>
        <li>
          <img src="static/img/siteseal_gd_3.gif" alt />
        </li>
        <li>
          <img src="static/img/pci.png" alt />
        </li>
        <li>
          <img src="static/img/xin.png" alt />
        </li>
        <li>
          <img src="static/img/chengxin.png" alt />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="less" scoped>
.footerWrap {
  width: 100%;
  background-color: #e6e6e6;
  padding: 10px 5%;
  .f1 {
    border-bottom: 2px solid #f67964;
    padding-bottom: 30px;
    text-align: center;
    h3 {
      font-size: 14px;
      margin-bottom: 10px;
    }
    p {
      line-height: 20px;
    }
    img {
      width: 80px;
    }
  }
  .foot {
    color: #a09e99;
    line-height: 30px;
    .footpic {
        display: flex;
        justify-content: center;
        align-items: center;
      li {
        float: left;
        margin: 0 15px;
      }
    }
  }
}
</style>