<template>
  <div class="">
    <div id="allback" class="allback">
      <h3 class="header__title">集团名称******</h3>
      <Row style="margin-top: 30px;">
        <Col class="t-c" :xs="{ span: 4, offset: 1 }" :lg="{ span: 4, offset: 1 }">
        <div class="sssr"><b>7024</b> 亿</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">25%</span><span class="ffftext">税收收入</span>
        </div>
        </Col>
        <Col class="t-c" :xs="{ span: 4, offset: 1 }" :lg="{ span: 4, offset: 1 }">
        <div class="zzs"><b>1990</b>亿</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">25%</span><span
          class="ffftext">增值税收入</span>
        </div>
        </Col>
        <Col class="t-c" :xs="{ span: 4, offset: 1 }" :lg="{ span: 4, offset: 1 }">
        <div class="sds"><b>24</b> 亿</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">35%</span><span
          class="ffftext">所得税收入</span>
        </div>
        </Col>
        <Col class="t-c" :xs="{ span: 4, offset: 1 }" :lg="{ span: 4, offset: 1 }">
        <div class="xfs"><b>24</b> 亿</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">25%</span><span
          class="ffftext">消费税税收入</span>
        </div>
        </Col>
        <Col class="t-c" :xs="{ span: 4 }" :lg="{ span: 4}">
        <div class="cyqy"><b>24</b> 个</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">25%</span><span
          class="ffftext">成员企业</span>
        </div>
        </Col>
      </Row>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'jtqkTotal',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        name: "开始"
      }
    },
    mounted: function () {
    },
    methods: {
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .spantext .icon-plus-select-up, .spantext .greentext {
    color: #22AB36;
    font-size: 12px;
    vertical-align: middle;
    font-weight: bold;
  }
  .spantext .ffftext {
    color: #65aad4;
    font-size: 12px;
    margin-left: 8px;
  }

  .sssr {
    color: #D0CACA;
    font-size: 24px;
  }

  .zzs {
    color: #D0CACA;
    font-size: 24px;
  }

  .sds {
    color: #D0CACA;
    font-size: 24px;
  }
  .xfs{
    color: #D0CACA;
    font-size: 24px;
  }
  .cyqy{
    color: #D0CACA;
    font-size: 24px;
  }

  .allback {
    position: relative;
    padding: 20px;
    height: 130px;
    background-image: url(../../../../assets/images/alljt.png);
    background-repeat: no-repeat;
    background-size: 100% 100%;
  }
  .header__title{
    position: absolute;
    top: 10px;
    left: 0;
    right: 0;
    z-index:99;
    color: #fff;
    text-align: center;
  }
</style>
