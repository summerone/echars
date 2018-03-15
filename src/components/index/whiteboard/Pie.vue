<!--menglihuan-->
<template>
  <div class="contents">
    <Row >
      <Col span="12"  style="height:250px;padding-right: 5px;">
      <div id="gzzbqk" class="pic" ></div>
     </Col>
      <Col span="12"  style="height:250px;padding-left: 5px;">
      <div id="gzzbqktwo" class="pic"></div>
      </Col>
    </Row>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'gzzbqk',
    data () {
      return {
      }
    },
    mounted:function(){
      setTimeout(this.gzzbqkFunction(),5000);
      setTimeout(this.gzzbqktwoFunction(),5000)
    },
    methods:{
      gzzbqkFunction(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('gzzbqk'));
        let  option = {
          title:
            [
              {
                text: '区域占比',
                x: 'center',
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
            right: 20,
            top:120,
            itemWidth:5,
            itemHeight:5,
            textStyle:{
              color: '#fff',
            },
            data:['其他行业','电力、热力、燃气及水生产和供应业']
          },
          color: ['#92CCCE','#FF5A00'],
          series: [
            {
              name:'区域占比',
              type:'pie',
              radius: ['40%', '60%'],
              center:['50%','60%'],
              avoidLabelOverlap: false,
              label: {
                formatter:'{d}%',
                position: 'outside',
                align: 'center',
                verticalAlign: 'top',
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
                {value:71, name:'其他行业'},
                {value:29, name:'电力、热力、燃气及水生产和供应业'}
              ]
            }
          ]
        };
        myChart.setOption(option);
      },
      gzzbqktwoFunction(){
        var myChart = Vue.prototype.echarts.init(document.getElementById('gzzbqktwo'));
        let  option = {
          title:
            [
              {
                text: '税种占比',
                x: 'center',
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
            right: 60,
            top:100,
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
              radius: ['40%', '60%'],
              center:['50%','60%'],
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
  .contents{
    position: relative;
    padding: 2px 5px 3px 2px;
    width: 100%;
    height: 100%;
  }
  .pic{
    padding:15px 0px;
    width: 100%;height:100%;
    /*text-align: center;*/
    background-image: url(../../../assets/images/allback.png);
    background-repeat: no-repeat,no-repeat;
    background-size: 100% 100%;
  }
</style>
