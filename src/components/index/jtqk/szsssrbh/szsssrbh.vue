<template>
  <div class="content__this">
    <div id="szsssrbh" class="pic" style="width: 100%; height: 280px;"></div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'szsssrbh',
    data () {
      return {}
    },
    mounted: function () {
      this.$nextTick(function () {
        setTimeout( this.szsssrbhFunction(),5000)
      });
    },
    methods: {
      szsssrbhFunction(){//同比图
        var myChart = Vue.prototype.echarts.init(document.getElementById('szsssrbh'));
        myChart.setOption({
          title: {
            text: '税种税收收入月变化',
            textStyle: {
              color: '#fff',
              fontWeight: 'bold',
              fontSize:16
            },
            x: 'center',
          },
          tooltip: {
            trigger: 'axis'
          },
          legend: {
            orient:'horizontal',
            right: 10,
            top:30,
            itemWidth:10,
            itemHeight:10,
            textStyle:{
              color: '#fff',
            },
            data:['增值税','所得税','消费税']
          },
          grid: {
            left: '0',
            right: '4%',
            bottom: '3%',
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
              data: [320, 332, 301, 334, 390, 8540, 320, 320, 5000, 301, 334, 900, 330, 320],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#9446DA',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#C2BD25',
                    width:2.5
                  },
                }
              },
            },
            {
              name: '所得税',
              type: 'line',
              stack: '总量',
              data: [820, 932, 901, 934, 1290, 1330, 1320, 320, 332, 301, 334, 390, 330, 320],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#D45849',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#D45849',
                  }
                }
              },
            },
            {
              name: '消费税',
              type: 'line',
              stack: '总量',
              data: [820, 932, 901, 934, 1290, 1330, 1320, 320, 332, 301, 334, 390, 330, 320],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#4F64D2',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#4F64D2',
                  }
                }
              },
            }
          ]
        });
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .content__this {
    /*padding: 10px;*/
  }

  .pic {
    padding: 10px 20px;
    /*background: #102B7C;*/
    border-radius: 8px;
    background-image: url(../../../../assets/images/titleftbj.png), url(../../../../assets/images/titrightbj.png);
    background-position: 20px 20px, 95% 20px;
    background-repeat: no-repeat, no-repeat;
  }
</style>
