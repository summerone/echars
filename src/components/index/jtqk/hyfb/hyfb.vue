<!--menglihuan
    集团在蓉区域分布-->
<template>
  <div class="content">
    <h3 class="picture__title">集团在蓉行业分布</h3>
    <div id="hyfb" class="pic" style="width: 100%;height:100%"></div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'hyfb',
    data () {
      return {
      }
    },
    mounted:function(){
      setTimeout(this.hyfbFunction(),5000);
    },
    methods:{
      hyfbFunction(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('hyfb'));

        let  option = {
          title:
            [
//              {
//                text: '行业户数占比',
//                left: 130,
//                top: 50,
//                textStyle: {
//                  color: '#fff',
//                  fontSize: '10',
//                  fontWeight: 'normal'
//                }
//              },
//              {
//                text: '行业税收收入占比',
//                left: 380,
//                top: 50,
//                textStyle: {
//                  color: '#fff',
//                  fontSize: '10',
//                  fontWeight: 'normal'
//                }
//              },
          ]
          ,
          tooltip: {
            trigger: 'item',
            formatter: "{a} <br/>{b}: {c} ({d}%)",
          },
          legend: {
            orient:'vertical',
            height:100,
            width:40,
            itemGap:12,
            itemWidth:10,
            itemHeight:4,
            left: 50,
            top:240,
            itemWidth:5,
            itemHeight:5,
            textStyle:{
              color: '#fff',
              fontSize:10
            },
            data:[
              {name:'批发和零售业',icon:'circle'
              },
              {name:'金融业',icon:'circle'
              },
              {name:'制造业',icon:'circle'
              },
              {name:'房地产业',icon:'circle'
              },
              {name:'建筑业',icon:'circle'
              },
              {name:'租赁和商务服务业',icon:'circle'
              },
              {name:'信息传输,软件和信息技术业',icon:'circle',
              },
              {name:'科学研究和技术服务业',icon:'circle'
              },
              {name:'交通运输,仓储和邮政业',icon:'circle'
              },
              {name:'电力,热力,燃气,及水生产和供应业',icon:'circle'
              },
              {name:'住宿和餐饮业',icon:'circle'
              },
              {name:'采矿业',icon:'circle'
              },
              {name:'农,林,牧,渔业',icon:'circle'
              },
              {name:'卫生和社会工作',icon:'circle'
              },
              {name:'教育',icon:'circle'
              },
              {name:'居民服务,修理和其他服务业',icon:'circle'
              },
              {name:'文化,体育,和娱乐业',icon:'circle'
              },
              {name:'水利,环境和公共设施管理业',icon:'circle'
              },
              {name:'公共管理,社会保障和社会组织',icon:'circle'
              }
            ]
          },
          color:['#2F319E',
            '#93ccce',
            '#e18197',
            '#e5D723A',
            '#F15A25',
            '#FBB03B',
            '#3AB54B',
            '#8DC73F',
            '#92C640',
            '#00FEF3',
            '#92065F',
            '#EE1F7A',
            '#E9E9E9',
            '#A0A0A0',
            '#603814',
            '#77277C',
            '#703814',
            '#8B5F38',
            '#998677',
            '#00FF00',
            '#005B2C',
            '#23B574',
            '#01A89E'],
          series: [
            {
              name:'行业户数占比',
              type:'pie',
              radius:  [0, '30%'],
              center : ['50%', '45%'],
              avoidLabelOverlap: false,
              label: {
                normal: {
                  show:false,
                  backgroundColor: '#093A72',
                  borderColor: '#aaa',
                  borderWidth: 1,
                  borderRadius: 4,
                  formatter:'{b|{b}}{abg|}\n{d|{d}户}',
                  position: 'outside',
                  align: 'center',
                  verticalAlign: 'top',
                  rich: {
                    b: {
                      color: '#fff',
                      lineHeight: 22,
                      align: 'center'
                    },
                    d: {
                      color: '#fff',
                      lineHeight: 22,
                      align: 'center'
                    },
                    abg:{
                      height: 22,
                      width: '100%',
                    }
                  }
                },
                emphasis: {
                  show: true
                }
              },
              labelLine: {
                normal: {
                  show: false,
                  length:30,
                },
                emphasis: {
                  show: true
                }
              },
              itemStyle: {
                emphasis: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              },
              data:[
                {name:'批发和零售业',value:5
                },
                {name:'金融业',value:5
                },
                {name:'制造业',value:5
                },
                {name:'房地产业',value:5
                },
                {name:'建筑业',value:5
                },
                {name:'租赁和商务服务业',value:5
                },
                {name:'信息传输,软件和信息技术业',value:5
                },
                {name:'科学研究和技术服务业',value:5
                },
                {name:'交通运输,仓储和邮政业',value:5
                },
                {name:'电力,热力,燃气,及水生产和供应业',value:5
                },
                {name:'住宿和餐饮业',value:5
                },
                {name:'采矿业',value:5
                },
                {name:'农,林,牧,渔业',value:5
                },
                {name:'卫生和社会工作',value:5
                },
                {name:'教育',value:5
                },
                {name:'居民服务,修理和其他服务业',value:5
                },
                {name:'文化,体育,和娱乐业',value:5
                },
                {name:'水利,环境和公共设施管理业',value:5
                },
                {name:'公共管理,社会保障和社会组织',value:10
                }
              ]
            },
            {
              name:'行业税收收入占比',
              type:'pie',
              radius:  ["35%", '45%'],
              center : ['50%', '45%'],
              avoidLabelOverlap: false,
              label: {
                normal: {
                  show:false,
                  backgroundColor: '#093A72',
                  borderColor: '#aaa',
                  borderWidth: 1,
                  borderRadius: 4,
                  formatter:'{b|{b}}{abg|}\n{d|{d}万元}',
                  position: 'outside',
                  align: 'center',
                  verticalAlign: 'top',
                  rich: {
                    b: {
                      color: '#fff',
                      lineHeight: 22,
                      align: 'center'
                    },
                    d: {
                      color: '#fff',
                      lineHeight: 22,
                      align: 'center'
                    },
                    abg:{
                      height: 22,
                      width: '100%',
                    }
                  }
                },
                emphasis: {
                  show: true
                }
              },
              labelLine: {
                normal: {
                  show: false,
                },
                emphasis: {
                  show: true
                }
              },
              itemStyle: {
//                      color: ['#f00','#0f0'],
                emphasis: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              },
              data:[
                {name:'批发和零售业',value:5
                },
                {name:'金融业',value:5
                },
                {name:'制造业',value:5
                },
                {name:'房地产业',value:5
                },
                {name:'建筑业',value:5
                },
                {name:'租赁和商务服务业',value:5
                },
                {name:'信息传输,软件和信息技术业',value:5,
                },
                {name:'科学研究和技术服务业',value:5
                },
                {name:'交通运输,仓储和邮政业',value:5
                },
                {name:'电力,热力,燃气,及水生产和供应业',value:5
                },
                {name:'住宿和餐饮业',value:5
                },
                {name:'采矿业',value:5
                },
                {name:'农,林,牧,渔业',value:5
                },
                {name:'卫生和社会工作',value:5
                },
                {name:'教育',value:5
                },
                {name:'居民服务,修理和其他服务业',value:5
                },
                {name:'文化,体育,和娱乐业',value:5
                },
                {name:'水利,环境和公共设施管理业',value:5
                },
                {name:'公共管理,社会保障和社会组织',value:10
                }
              ]
            },
          ]
        };
        myChart.setOption(option);
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .content{
    position: relative;
    padding: 2px 5px 3px 2px;
    width: 100%;
    height: 100%;
    background-color: #102B7C;
    background-image: url('../../../../assets/images/box_hsline.png'),
    url('../../../../assets/images/box_hsline.png'),
    url('../../../../assets/images/box_ssline.png'),
    url('../../../../assets/images/box_ssline.png'),
    url('../../../../assets/images/titleftbj.png'),
    url('../../../../assets/images/titrightbj.png');
    background-repeat: no-repeat;
    background-position: top center,bottom center,left center, right center, left top,right top;
    background-origin: padding-box,padding-box,padding-box,padding-box,content-box,content-box;
    background-size: 98% auto, 98% auto,auto 98%,auto 98%,auto auto,auto auto;
  }
  .pic{
    background: #093a72;
    /*border-radius:2px ;*/
    text-align: center;
    background-image: url(../../../../assets/images/titleftbj.png),url(../../../../assets/images/titrightbj.png) ;
    background-position: 20px 20px, 95% 20px;
    background-repeat: no-repeat,no-repeat;
  }
  .picture__title{
    position: absolute;
    top:20px;
    left: 0;
    right: 0;
    z-index: 99;
    text-align: center;
    color: #fff;
  }
</style>

