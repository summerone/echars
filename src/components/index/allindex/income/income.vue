<template>
  <div class="content">
    <div id="main" class="hello" style="width: 100%; height: 200px;"></div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'HelloWorld',
    data () {
      return {}
    },
    mounted: function () {
      this.iconmFunction();//同比图
    },
    methods: {
      iconmFunction(){//同比图
        var myChart = Vue.prototype.echarts.init(document.getElementById('main'));
        myChart.setOption({
          title: {
            text: '同比收入情况比',
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
            data:['去年','今年']
          },

          toolbox: {
            show: false,
            orient: 'vertical',
            left: 'right',
            top: 'center',
            feature: {
              dataView: {readOnly: false},
              restore: {},
              saveAsImage: {}
            }
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
                color: ['#64B6ED'],
                opacity: 0.5
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
              name: '去年',
              type: 'line',
              stack: '总量',
              data: [320, 332, 301, 334, 390, 8540, 320, 320, 5000, 301, 334, 900, 330, 320],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#D05640',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#A8AF1F',
                    width:2.5
                  },
                }
              },
            },
            {
              name: '今年',
              type: 'line',
              stack: '总量',
              data: [820, 932, 901, 934, 1290, 1330, 1320, 320, 332, 301, 334, 390, 330, 320],
              symbol: 'circle',     //设定为实心点
              symbolSize: 10,   //设定实心点的大小
              itemStyle: {
                normal: {
                  color: '#9544E5',
                  borderColor: '#fff',
                  borderWidth: 2,
                  lineStyle: {
                    color: '#4479F0',
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
  .content {
    padding: 10px;
  }

  .hello {
    padding: 10px 20px;
    background: #102B7C;
    border-radius: 8px;
    background-image: url(../../../../assets/images/titleftbj.png), url(../../../../assets/images/titrightbj.png);
    background-position: 20px 20px, 95% 20px;
    background-repeat: no-repeat, no-repeat;
  }
</style>
