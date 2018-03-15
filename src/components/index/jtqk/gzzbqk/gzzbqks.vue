<!--menglihuan 各种纳税情况小-->
<template>
  <div class="content__this">
    <div id="gzzbqks" class="pic" style="width: 100%;height:100%"></div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'gzzbqks',
    data () {
      return {
      }
    },
    mounted:function(){
      this.gzzbqksFunction();
    },
    methods:{
      gzzbqksFunction(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('gzzbqks'));

        let  option = {
          title:
            [
              {
                text: '各税种占比概况',
                left: 100,
                top: 12,
                textStyle: {
                  color: '#fff',
                  fontSize: '17',
                  fontWeight: 'normal'
                }
              },
            ]
          ,
          tooltip: {
            trigger: 'item',
            formatter: "{a} <br/>{b}: {c} ({d}%)",
          },
          legend: {
            orient: 'vertical',
            right: 10,
            top:200,
            itemWidth:5,
            itemHeight:5,
            textStyle:{
              color: '#fff',
            },
            data:['增值税','所得税','消费税']
          },
          color: ['#93ccce','#e18197','#8abe6e'],
          series: [
            {
              name:'各税种占比概况',
              type:'pie',
              radius: ['30%', '45%'],
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
//                      color: ['#f00','#0f0'],
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
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .content__this{
    padding: 2px 5px 3px 2px;
    width: 100%;
    height: 100%;
  }
  .pic{
    /*background: #102B7C;*/
    /*border-radius:2px ;*/
    text-align: center;
    background-image: url(../../../../assets/images/titleftbj.png),url(../../../../assets/images/titrightbj.png) ;
    background-position: 20px 20px, 95% 20px;
    background-repeat: no-repeat,no-repeat;
  }
</style>
