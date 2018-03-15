<!--menglihuan
    集团在蓉区域分布-->
<template>
  <div class="content">
    <h3 class="picture__title">集团在蓉区域分布</h3>
    <div id="qyfb" class="pic" style="width: 100%;height:100%"></div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'qyfb',
    data () {
      return {
      }
    },
    mounted:function(){
      setTimeout( this.qyfbFunction(),5000)
    },
    methods:{
      qyfbFunction(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('qyfb'));

        let  option = {
          title:
            [
//              {
//                text: '区户数占比',
//                left: 130,
//                top: 50,
//                textStyle: {
//                  color: '#fff',
//                  fontSize: '10',
//                  fontWeight: 'normal'
//                }
//              }
//              ,
//              {
//                text: '区税收收入占比',
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
//            itemWidth:10,
//            itemHeight:4,
            left: 110,
            top:240,
            itemWidth:5,
            itemHeight:5,
            textStyle:{
              color: '#fff',
              fontSize:10
            },
            data:[
              {name:'龙泉驿',icon:'circle'
              },
              {name:'高新区',icon:'circle'
              },
              {name:'彭州市',icon:'circle'
              },
              {name:'武侯区',icon:'circle'
              },
              {name:'青羊区',icon:'circle'
              },
              {name:'锦江区',icon:'circle'
              },
              {name:'成华区',icon:'circle',
              },
              {name:'金牛区',icon:'circle'
              },
              {name:'新都区',icon:'circle'
              },
              {name:'温江区',icon:'circle'
              },
              {name:'双流区',icon:'circle'
              },
              {name:'青白江区',icon:'circle'
              },
              {name:'都江堰',icon:'circle'
              },
              {name:'郫县',icon:'circle'
              },
              {name:'天府新区',icon:'circle'
              },
              {name:'崇州市',icon:'circle'
              },
              {name:'新津县',icon:'circle'
              },
              {name:'邛崃市',icon:'circle'
              },
              {name:'金堂县',icon:'circle'
              },
              {name:'大邑县',icon:'circle'
              },
              {name:'简阳市',icon:'circle'
              },
              {name:'浦江县',icon:'circle'
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
              name:'区户数占比',
              type:'pie',
              radius:  [0, '30%'],
              center : ['50%', '40%'],
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
//                      color: ['#f00','#0f0'],
                emphasis: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              },
              data:[
                {value:5, name:'龙泉驿'},
                {value:5, name:'高新区'},
                {value:5, name:'彭州市'},
                {value:5, name:'武侯区'},
                {value:5, name:'青羊区'},
                {value:5, name:'锦江区'},
                {value:5, name:'成华区'},
                {value:5, name:'金牛区'},
                {value:5, name:'新都区'},
                {value:5, name:'温江区'},
                {value:5, name:'双流区'},
                {value:5, name:'青白江区'},
                {value:5, name:'都江堰'},
                {value:5, name:'郫县'},
                {value:5, name:'天府新区'},
                {value:5, name:'崇州市'},
                {value:5, name:'新津县'},
                {value:5, name:'邛崃市'},
                {value:2, name:'金堂县'},
                {value:2, name:'大邑县'},
                {value:2, name:'简阳市'},
                {value:4, name:'浦江县'},
              ]
            },
            {
              name:'区税收收入占比',
              type:'pie',
              radius: ['35%', '45%'],
              center : ['50%', '40%'],
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
                {value:5, name:'龙泉驿'},
                {value:5, name:'高新区'},
                {value:5, name:'彭州市'},
                {value:5, name:'武侯区'},
                {value:5, name:'青羊区'},
                {value:5, name:'锦江区'},
                {value:5, name:'成华区'},
                {value:5, name:'金牛区'},
                {value:5, name:'新都区'},
                {value:5, name:'温江区'},
                {value:5, name:'双流区'},
                {value:5, name:'青白江区'},
                {value:5, name:'都江堰'},
                {value:5, name:'郫县'},
                {value:5, name:'天府新区'},
                {value:5, name:'崇州市'},
                {value:5, name:'新津县'},
                {value:5, name:'邛崃市'},
                {value:2, name:'金堂县'},
                {value:2, name:'大邑县'},
                {value:2, name:'简阳市'},
                {value:4, name:'浦江县'},
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
