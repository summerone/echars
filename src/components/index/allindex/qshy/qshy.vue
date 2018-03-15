<template>
  <div class="content">
    <div  class="hello "  style="width: 100%; height:100%;">
      <div class="title"><h5 >行业状况</h5></div>
      <!--tab 切换-->
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
      <!--picture-->
      <div id="firstten" style="width: 100%; height:454px;"></div>
    </div>
    <!--更多弹框-->
    <v-dialog v-if="isShow">
      <v-more slot="content"></v-more>
    </v-dialog>
  </div>
</template>

<script>
  import Vue from 'vue'
  import VDialog from "../../../dialog/Modal"
  import VMore from './More.vue'
  export default {
    name: 'HelloWorld',
    components:{
      VDialog,
      VMore,
    },
    data () {
      return {
        tab1: true,
        tab2: false,
        isShow: false
      }
    },
    mounted:function(){
      this.regions();//前十区域
    },
    methods:{
      regions(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('firstten'))
          ,self = this;
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
            left: '2%',
            right: '2%',
            top: '18%',
            bottom: '5%',
            containLabel: true
          },
          xAxis: {
            data: ['1.制造业', '2.金融业', '3.批发和零售业', '4.信息传输、软件和信息技术服务业', '5.房地产业', '6.电力、热力、燃气及水产和供应业','7.科学研究和技术服务业', '8.建筑业','9.9.交通运输、仓储和邮政业', '10.租赁和商务服务业'],
            axisLabel:{
              interval:0,
              rotate:45,//倾斜度 -90 至 90 默认为0
              margin:15,
              textStyle:{
                color:'#D9E1FF'
              },
              formatter: function (params) {
                return self.tool.trunc(params,24);
              }
            },
            axisTick: {
              show: false
            },
            splitLine: {
              show: false,
            },
            axisLine:{
              lineStyle:{
                color:'#64B6ED',
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
            barWidth: 12,
            itemStyle:{
              normal:{
                color:'#ACCBEA'
              }
            },
            data: [36540, 29540, 36546, 185410, 88520, 298540,36540, 29540, 36546, 185410]
          }]
        });
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  span.morth{line-height: 8px;}
  .incomeTen,.floatedten{
    display: inline-block;
    line-height: 35px;
    font-size: 12px;
    color: #3969C8;
  }
  .floatedten{margin-left: 18px;}
  .incomeTen{margin-left: 6px;color: #5CBCF1}
  .title{
    color: #fff;
    width: 100%;
    text-align: center;
    font-size: 20px;
  }
  /*.content{*/
    /*padding: 10px;*/
  /*}*/
  .regionsHello{
    position: absolute;
    left: 20px;
    right: 20px;
    top: 50px;
    z-index: 99;
    height: 40px;
    background-image: url(../../../../assets/images/qten.png);
    background-repeat: no-repeat;
    background-size: 100% 30px;
  }
  .hello{
    position: relative;
    padding: 10px 20px;
    background: #102B7C;
    border-radius:8px ;
    background-image: url(../../../../assets/images/titleftbj.png),
    url(../../../../assets/images/titrightbj.png),
    url('../../../../assets/images/box_hsline.png'),
    url('../../../../assets/images/box_hsline.png'),
    url('../../../../assets/images/box_ssline.png'),
    url('../../../../assets/images/box_ssline.png');
    background-position: 20px 20px, 95% 20px ,top center,bottom center,left center, right center;
    background-repeat: no-repeat;
  }

  /*切换 css - start*/
  .tab_more{
    position: absolute;
    left: 20px;
    right: 20px;
    top: 50px;
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
    width: 80px;
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
    left: 74px;
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
    width: 200px;
    background-color: #4187CA;
    position: absolute;
    bottom: 0;
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
