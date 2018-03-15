<template>
  <div class="content">
    <div class="hello " style="width: 100%; height:269px;">
      <div class="title"><span>区域状况</span></div>
      <!--<div class="regionsHello">-->
        <!--<span class="incomeTen cursor">-->
          <!--&lt;!&ndash;<span class='incomeBack'></span>&ndash;&gt;-->
          <!--收入前十-->
        <!--</span>-->
        <!--<span class="floatedten cursor">-->
          <!--增浮前十-->
        <!--</span>-->
        <!--<span class="floatedten pull-right morth cursor" @click="isShow = !isShow">-->
          <!--更多-->
          <!--<i class="iconfont icon-gengduo"></i>-->
        <!--</span>-->
      <!--</div>-->
      <!--图切换还有更多-->
      <div class="tab_more">
      <span class="tab tab__one f12 cursor f-color" :class="{active: tab1}" @click="tab1 = true;tab2 = false">
        入库前十
      </span>
        <span class="tab tab__two f12 cursor f-color" :class="{active: tab2}" @click="tab1 = false;tab2 = true">
        增浮前十
      </span>
        <a href="javascript:;" class="more cursor f-color" @click="isShow = !isShow">
          更多
          <i class="iconfont icon-gengduo"></i>
        </a>
        <span class="bot__line"></span>
      </div>
      <!--charts-->
      <div id="regions" style="width: 100%; height:250px;top:-40px;"></div>
    </div>
    <!--更多弹框-->
    <v-dialog v-if="isShow">
      <v-moreqy slot="content"></v-moreqy>
    </v-dialog>
  </div>
</template>

<script>
  import Vue from 'vue'
  import VDialog from "../../../dialog/Modal"
  import VMoreqy from './Moreqy.vue'
  export default {
    name: 'HelloWorld',
    components:{
      VDialog,
      VMoreqy,
    },
    data () {
      return {
        tab1: true,
        tab2: false,
        msg: 'Welcome to Your Vue.js App',
        name: "开始",
        isShow: false
      }
    },
    mounted: function () {
      this.regions();//前十区域
    },
    methods: {
      regions(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('regions'));
        myChart.setOption({
          title: {
//            text: '前十区域',
            textStyle: {
              color: '#fff',
              fontWeight: 'normal',
            },
            x: 'center',
          },
          tooltip: {},
          grid: {
            left: '0',
            right: '4%',
            top: '40%',
            bottom: '-3%',
            containLabel: true
          },
          xAxis: {
            data: ['1.龙泉驿区', '2.高新区', '3.彭州区', '4.青羊区', '5.武侯区', '6.锦江区', '7.成华区', '8.金牛区', '9.新都区', '10.双流区'],
            axisLabel: {
              interval: 0,
              rotate: 45,//倾斜度 -90 至 90 默认为0
              margin: 15,
              textStyle: {
                color: '#D9E1FF'
              }
            },
            axisTick: {
              show: false
            },
            splitLine: {
              show: false,
            },
            axisLine: {
              lineStyle: {
                color: '#64B6ED',
              }
            },
          },
          yAxis: {
            splitLine: {
              show: true,
              //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED'],
                opacity: 0.5
              },
            },
            axisLine: {
              show: false
            },
            axisLabel: {
              textStyle: {
                color: '#D9E1FF',
              },
            },
          },
          series: [{
            name: '销量',
            type: 'bar',
            barWidth: 20,
            itemStyle: {
              normal: {
                color: '#78D877'
              }
            },
            data: [365400, 29540, 36546, 185410, 88520, 298540, 36540, 29540, 36546, 185410]
          }]
        });
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  span.morth {
    line-height: 17px;
  }

  .incomeTen, .floatedten {
    display: inline-block;
    line-height: 40px;
    font-size: 12px;
    color: #3969C8;
  }

  .floatedten {
    margin-left: 50px;
  }

  .incomeTen {
    margin-left: 20px;
    color: #5CBCF1
  }

  .title {
    width: 100%;
    text-align: center;
    font-size: 20px;
    color: #fff;
  }

  .content {
    padding: 10px;
  }

  .regionsHello {
    position: absolute;
    left: 20px;
    right: 20px;
    top: 36px;
    z-index: 99;
    height: 36px;
    margin-top: 10px;
    background-image: url(../../../../assets/images/qten.png);
    background-repeat: no-repeat;
    background-size: 100% 35px;
  }

  .hello {
    position: relative;
    padding: 10px 20px;
    background: #102B7C;
    border-radius: 8px;
    background-image: url(../../../../assets/images/titleftbj.png), url(../../../../assets/images/titrightbj.png);
    background-position: 20px 20px, 95% 20px;
    background-repeat: no-repeat, no-repeat;
  }

  /*切换 css - start*/
  .tab_more{
    position: absolute;
    left: 20px;
    right: 20px;
    top: 44px;
    z-index: 99;
    height: 38px;
    line-height: 41px;
    /*background-image: url(../../../assets/images/qten.png);*/
    background-position: center bottom;
    background-repeat: no-repeat;
    background-size: 100% 32px;
    /*border-bottom: 1px solid #4187CA;*/
    /*box-shadow: inset 0 -1px 0 #4187CA;*/
  }
  .tab{
    position: absolute;
    bottom: 0;
    display: inline-block;
    padding-left: 12px;
    width: 110px;
    /*height: 32px;*/
    height: 28px;
    line-height: 30px;
    text-align: left;
    background-image: url(../../../../assets/images/bot.png);
    background-repeat: no-repeat;
    background-position: center bottom;
    background-size: 100% 100%;
  }
  .tab__one{
    left: 0;
  }
  .tab__two{
    left: 100px;
  }
  .more{
    display: inline-block;
    position: absolute;
    right: 0;
    bottom: 0;
    overflow: hidden;
    z-index: 200;
    width: 60px;
    height: 38px;
    text-align: right;
    font-size: 12px;
    line-height: 14px;
    background-image: url('../../../../assets/images/line.png');
    background-repeat: no-repeat;
    background-position: left bottom;
    background-size: 100% auto;
  }
  .bot__line{
    display: inline-block;
    height: 1px;
    /*width: 200px;*/
    background-color: #4187CA;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 60px;
  }
  .f-color{
    color: #60c0fb;
  }
  .active{
    z-index: 111;
    height: 32px;
    line-height: 38px;
    color: #fff !important;
    background-image: url(../../../../assets/images/botselct.png);
    background-size: 100% 100%;
  }
  /*切换 css - end*/
</style>
