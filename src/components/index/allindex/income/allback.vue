<template>
  <div class="content">
    <div id="allback" class="allback">
      <div class="text-center">
        <span class="backall">整体情况</span>
        <span class="timeback">截止数据到2017年12月</span>
      </div>
      <Row style="margin-top: 10px;">
        <Col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }">
        <div class="yiyuan" ><b style=" font-family: 'Impact Regular';">681.9</b> 亿</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">15%</span><span
          class="ffftext">税收收入</span>
        </div>
        </Col>
        <Col :xs="{ span: 11, offset: 1 }" :lg="{ span: 6, offset: 2 }">
        <div class="fushu" ><b style=" font-family: 'Impact Regular';">3375</b> 户</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">15%</span><span
          class="ffftext">集团户数</span>
        </div>
        </Col>
        <Col :xs="{ span: 5, offset: 1 }" :lg="{ span: 6, offset: 2 }">
        <div class="nummber" ><b style=" font-family: 'Impact Regular';">45782</b> 个</div>
        <div class="spantext">
          <i class="iconfont icon-plus-select-up"></i><span class="greentext">15%</span><span
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
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        name: "开始"
      }
    },
    mounted: function () {
    },
    methods: {}
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
    color: #fff;
    font-size: 12px;
    margin-left: 8px;
  }

  .yiyuan {
    color: #7CD972;
    font-family: 'Impact Regular';
    font-weight: 300;
    font-size: 25px;
  }

  .fushu {
    color: #FFC43B;
    font-weight: 300;
    font-size: 25px;
  }

  .nummber {
    color: #94CCC8;
    font-weight: 300;
    font-size: 25px;
  }

  .timeback {
    display: block;
    color: #60B8EB;
    font-size: 12px;
  }

  .backall {
    color: #fff;
    font-size: 20px;
  }

  .allback {
    padding: 20px;
    height: 180px;
    background-image: url(../../../../assets/images/allback.png);
    background-repeat: no-repeat;
    background-size: 100%;
  }

  .content {
    padding: 10px;
  }
</style>
