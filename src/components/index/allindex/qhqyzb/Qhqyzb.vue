<template>
  <!--千户占比-->
  <div id="qhqyzb" class="qhqyzb__box">
    <h3 class="picture__title">千户集团占比概况</h3>
    <div id="qhqyzb_picture" class="qhqyzb_picture"></div>
  </div>
</template>
<script>
  export default {
      name: 'Qhqyzb',
      data() {
          return {
              option:  {
                title :
                  [{
                      text: '千户纳税人全市占比',
                      left: 'left',
                      top: 'bottom',
                      textStyle: {
                          color: '#fff',
                          fontSize: '12',
                          fontWeight: 'normal'
                      }
                    },
                    {
                          text: '千户纳税人收入全市占比',
                          left: 'right',
                          top: 'bottom',
                          textStyle: {
                            color: '#fff',
                            fontSize: '12',
                            fontWeight: 'normal'
                          }
                      }],
                tooltip : {
                  trigger: 'item',
                  formatter: "{a} <br/>{b} : {c} ({d}%)",
                  textStyle:{
                    fontSize:12
                  }
                },
                color: ['#fdbc39','#77d877'],
                series : [
                  {
                    name: '千户纳税人全市占比',
                    type: 'pie',
                    startAngle: 180,
                    radius : ['20%','35%'],
                    center : ['30%', '50%'],
                    data:[
                      {value:500, name:'千户纳税人'},
                      {value:1548, name:'全市纳税人'}
                    ],
                    label: {
                      formatter:"{b}\n{d}%",
                      position: 'outside',
                      width:'5%',
                    },
                    labelLine: {
                        length: 5,
                        length2: 5
                    },
                    itemStyle: {
//                      color: ['#f00','#0f0'],
                      emphasis: {
                        shadowBlur: 10,
                        shadowOffsetX: 0,
                        shadowColor: 'rgba(0, 0, 0, 0.5)'
                      }
                    }
                  },
                  {
                    name: '千户纳税人收入全市占比',
                    type: 'pie',
                    startAngle: 180,
                    radius : ['20%','35%'],
                    center : ['65%', '50%'],
                    data:[
                      {value:1000, name:'千户纳税人税收收入'},
                      {value:1548, name:'全市纳税人收入'}
                    ],
                    labelLine: {
                      length: 5,
                      length2: 5
                    },
                    itemStyle: {
                      emphasis: {
                        shadowBlur: 10,
                        shadowOffsetX: 0,
                        shadowColor: 'rgba(0, 0, 0, 0.5)'
                      }
                    }
                  }
                ]
              },
              option2: {
                tooltip: {
                  trigger: 'item',
                  formatter: "{a} <br/>{b}: {c} ({d}%)",
                  fontSize: 12
                },
                color: ['#fdbc39','#77d877'],
                series: [
                  {
                    name:'千户纳税人全市占比',
                    type:'pie',
                    startAngle: 180,
                    selectedMode: 'single',
                    radius: [0, '30%'],
                    center : ['50%', '60%'],
                    label: {
                      formatter:"{b}\n{d}%",
                      position: 'outside',
                    },
                    labelLine: {
                      length2: 25
                    },
                    data:[
                      {value:335, name:'千户纳税人'},
                      {value:1548, name:'全市纳税人'}
                    ]
                  },
                  {
                    name:'千户纳税人收入全市占比',
                    type:'pie',
                    startAngle: 180,
                    radius: ['40%', '55%'],
                    center : ['50%', '60%'],
                    label: {
                      formatter:"{b}\n{d}%",
                      position: 'outside',
                      fontSize: 12
                    },
                    data:[
                      {value:1000, name:'千户纳税人税收收入',itemStyle:{color: '#ffb753'}},
                      {value:1548, name:'全市纳税人收入',itemStyle: {color: '#f79441'}}
                    ]
                  }
                ]
              }
          }
      },
      mounted: function () {
          var self = this;
          self.dataInit(self.option2);
//          setTimeout(function () {
//            self.dataInit(self.option2);
//          },3000);
      },
      methods: {
          dataInit: function (option) {
              var echarts =  this.echarts.init(document.getElementById('qhqyzb_picture'));
              echarts.setOption(option);
          }
      }
  }
</script>
<style scoped="">
  .qhqyzb__box{
    position: relative;
    padding: 20px;
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
  .qhqyzb_picture{
    width: 100%;
    height: 100%;
  }
  .picture__title{
    position: absolute;
    left: 0;
    right: 0;
    z-index: 99;
    text-align: center;
    color: #fff;
  }
</style>
