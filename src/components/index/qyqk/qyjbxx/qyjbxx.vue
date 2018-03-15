<template>
  <div class="bg__common qyjbxx">
    <!--头部区域-->
    <h3 class=" header">
       企业基本信息
    </h3>
    <!--名称税号区域-->
    <Row class="cf">
      <Col span="16">
        <div class="dis_ib">
          <img class="qy__logo" src="../../../../assets/images/logo_qy.png">
        </div>
        <div class="dis_ib name__title-color">
          <ul >
            <li>
              <span>名称：</span><span>上海浦东发展银行股份有限公司成都分公司</span>
            </li>
            <li>
              <span>税号：</span><span>5148445555</span>
            </li>
          </ul>
        </div>
      </Col>
      <Col span="4">
        <div class="name__title-color">法定代表人</div>
        <div class="content__text-color">夏吉国</div>
      </Col>
      <Col span="4">
        <div class="name__title-color">注册资本</div>
        <div class="content__text-color">500万</div>
      </Col>
    </Row>
    <!--中间分割线区域-->
    <div class="fgx">
      <hr class="hr-ys">
    </div>
    <Row class="content__text-color">
      <Col span="14">
        <ul>
          <li>
            <span>主管税务机关：</span>
            <span>成都市国家税务局</span>
          </li>
          <li>
            <span>行业小类：</span>
            <span>公共管理、社会保障和社会组织</span>
          </li>
          <li>
            <span>行业大类：</span>
            <span>公共管理、社会保障和社会组织</span>
          </li>
        </ul>
      </Col>
      <Col span="10">
        <ul>
          <li>
            <span>总分机构类型：</span>
            <span>张三</span>
          </li>
          <li>
            <span>注册类型：</span>
            <span>成都市国家税务局</span>
          </li>
          <li>
            <span>股东及占比：</span>
            <span></span>
          </li>
        </ul>
      </Col>
    </Row>
  </div>
</template>
<script>
  import Vue from 'vue'
  export default {
    name: 'qyjbxx',
    data () {
      return {
      }
    },
    mounted: function () {
    },
    methods: {
    }
  }
</script>
<style scoped>
  .name__title-color{
    color: #67c2fb;
  }
  .content__text-color{
    color: #d5deff;
  }
  .dis_ib{
    display: inline-block;
    vertical-align: middle;
  }
  .qy__logo{
    width: 50px;
    height: 50px;
    vertical-align: middle;
    margin-right: 10px;
  }
  .bg__common{
    background-image: url(../../../../assets/images/allback.png);
    background-repeat: no-repeat;
    background-size: 100% 100%;
  }
  .qyjbxx{
    width: 100%;
    height: 100%;
    padding: 20px;
  }

  .header{
    height: 30px;
    color: #fff;
    text-align: center;
    margin: 10px 0;
  }
  .name-a{
    margin-left: 2%;
    color: #81b5f9;
  }
  .name-b{
    margin-left: 18%;
  }
  .hr-ys{
    border: none;
    background-color: #2b56a0;
    height: 1px;
  }
  .fgx{
    margin: 30px 0 20px 0;
  }
  .info{
    margin-bottom: 3%;
    color: #fff;
  }
  .info-b{
    margin-right: 15%;
  }

  /*公共样式*/
  .fl{
    float: left;
  }
  .fr{
    float: right;
  }
  .cl-f{
    overflow: hidden;
  }
  .col-w{
    color: #d4d2d2;
    font-size: 13px;
  }
  .col-w-a{
    font-size: 11px;
    color: #fff;
  }
  .text-a{
    color: #339cf9;
    font-size: 11px;
  }
</style>
