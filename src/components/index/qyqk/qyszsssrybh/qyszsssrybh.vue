<template>
  <div class="qyszsssrybh">
    <!--头部区域-->
    <h3 class="header__title">企业税种税收收入月变化</h3>

    <!--图标区域-->
    <div id="con-qyszsssrybh" style="width: 100%;height:100%;"></div>
  </div>
</template>
<script>
  export default {
    name: 'qyszsssrybh',
    data () {
      return {
      }
    },
    mounted: function () {
        this.$nextTick(function () {
          this.qyszsssrybhFun();
        });
    },
    methods: {
      qyszsssrybhFun(){
        var myChart = this.echarts.init(document.getElementById('con-qyszsssrybh'));

        let option = {
          tooltip: {
            trigger: 'axis'
          },
          legend: {
            orient:'horizontal',
            top: 25,
            right: 10,
            itemWidth:10,
            itemHeight:10,
            textStyle:{
              color: '#fff',
            },
            data:['增值税','所得税','消费税']
          },
          grid: {
            left: '2%',
            right: '2%',
            bottom: '2%',
            top:'25%',
            containLabel: true
          },
          xAxis: {
            type: 'category',
            boundaryGap: false,
            data: ['01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12'],
            axisLine: {
              lineStyle: {
                color: '#64B6ED',
              }
            },
            axisTick: {
              show: false
            },
            splitLine: {
              show: false,
            },
            axisLabel: {
              textStyle: {
                color: '#D9E1FF',
              },
            },
            nameTextStyle: {
              color: '#D0D4FC'
            },
          },
          yAxis: {
            type: 'value',
            min:0,
            max: 3500000,
            splitNumber: 7,
            splitLine: {
              show: true,  //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED']
              }
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
          series: [
            {
              name: '增值税',
              type: 'line',
              stack: '总量',
              data: [1000000, 1500000, 1300000, 2500000, 3500000, 2800000, 1600000, 580000, 1050000, 2000000, 1200000, 650000],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              showSymbol:true,
              itemStyle: {
                normal: {
                  color: '#ffed27',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#c6ce3d',
                    width:2.5
                  },
                }
              },
            },
            {
              name: '所得税',
              type: 'line',
              stack: '总量',
              data: [100000, 500000, 2300000, 1500000, 2500000, 800000, 2600000, 1580000, 2050000, 1500000, 1500000, 1050000],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#ed5d28',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#7c4e59'
                  }
                }
              },
            },
            {
              name: '消费税',
              type: 'line',
              stack: '总量',
              data: [3000000, 2500000, 2300000, 3000000, 1050000, 1800000, 2600000, 1050000, 650000, 1800000, 2200000, 1650000],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#3878f4',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#245ec2'
                  }
                }
              },
            }
          ]
        };
        myChart.setOption(option);
      }
    }
  }
</script>
<style scoped>
  .qyszsssrybh{
    position: relative;
    width: 100%;
    height: 100%;
    padding: 20px;
    background-image: url(../../../../assets/images/titleftbj.png),
    url(../../../../assets/images/titrightbj.png);
    background-repeat: no-repeat;
    background-origin: content-box;
    background-position: top left, right top;
  }
  .header__title{
    position: absolute;
    color: #fff;
    top: 18px;
    left: 0;
    right: 0;
    text-align: center;
    z-index: 99;
  }
</style>
