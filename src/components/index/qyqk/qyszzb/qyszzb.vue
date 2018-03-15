<template>
  <div class="qyszzb bg__common">
    <!--头部区域-->
    <h3 class="header__title">企业税种占比</h3>
    <!--文本区域-->
    <div class="charts__item" id="con-qyszzb" style="width: 100%;height:100%;"></div>
  </div>
</template>
<script>
  import Vue from 'vue'
  export default {
    name: 'qyszzb',
    data () {
      return {
      }
    },
    mounted: function () {
        this.$nextTick(function () {
          this.qyszzbFun();
        })
    },
    methods: {
      qyszzbFun(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('con-qyszzb'));
        let  option = {
          tooltip: {
            trigger: 'item',
            formatter: "{a} <br/>{b}: {c} ({d}%)",
          },

          legend: {
            orient: 'vertical',
            right: 50,
            top:50,
            itemWidth:5,
            itemHeight:5,
            textStyle:{
              color: '#fff',
            },
            data:[
              {
                name:'增值税',
                icon: 'circle'
              },{
                name:'所得税',
                icon: 'circle'
              },{
                name:'消费税',
                icon: 'circle'
              }
            ]
          },
          color: ['#93ccce','#e18197','#8abe6e'],
          series: [
            {
              name:'企业税种占比',
              type:'pie',
              radius: ['45%', '65%'],
              center : ['50%', '55%'],
              avoidLabelOverlap: false,
              label: {
                formatter:'{d}%',
                position: 'outside',
                align: 'center',
                verticalAlign: 'top'
              },
              labelLine: {
              },
              itemStyle: {
                emphasis: {
                  shadowBlur: 10,
                  shadowOffsetX: 0,
                  shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
              },
              data:[
                {value:51, name:'增值税'},
                {value:24.8, name:'所得税'},
                {value:24.2, name:'消费税'}
              ]
            }
          ]
        };
        myChart.setOption(option);
      }
    }
  }
</script>
<style scoped>
  .qyszzb{
    width: 100%;
    height: 100%;
    position: relative;
    padding: 20px;
  }
  .bg__common{
    background-image: url(../../../../assets/images/allback.png);
    background-repeat: no-repeat;
    background-size: 100% 100%;
  }
  .charts__item{
    width: 100%;
    height: 100%;
  }
  .header__title{
    position: absolute;
    color: #fff;
    top: 20px;
    left: 0;
    right: 0;
    text-align: center;
    z-index: 99;
  }
</style>
