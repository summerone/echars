<template>
  <!--行业分布: 更多-->
  <div  class="component__box">
    <h3 class="chart__title">区域分布</h3>
    <!--tab-->
    <ul class="tab__charts">
      <li v-for="(item, index) in tab" :key="index" :class="{active: item.state}" @click="handlerClick(index)">{{item.name}}</li>
    </ul>
    <div id="component_chart" class="component__chart" style="width: 100%;height: 100%"></div>
  </div>
</template>
<script>
  export default {
    name: 'Hyfbmodal',
    data() {
      var self = this;
      return {
        tab: [{name: '区域税收情况',state: true},{name: '区域增长率情况',state: false},{name: '区域税收情况',state: false},{name: '区域税收增长率',state: false}],
        data1: [1054100, 2000000, 36546, 185410, 2000000, 298540,36540, 29540, 2000000, 185410, 2000000, 36546, 185410, 2000000, 298540,36540, 29540, 2000000],
        option1: {
          title: {
            textStyle: {
              color: '#fff',
              fontWeight: 'normal',
            },
            x: 'center',
          },
          tooltip: {
//           position: ['35%','20%'],
            formatter: '{b}<br />{c}',
            textStyle:{
              fontSize:12
            }
          },
          grid: {
            left:'10%',
            right: '5%',
            top: '30%',
            bottom:'30%'
          },
          xAxis: {
            data: ['龙泉驿区', '高新区', '彭州市', '青羊区', '武侯区', '锦江区', '成华区',
              '金牛区', '新都区', '双流区','温江区', '青白江区', '都江堰市', '郫县','天府新区', '崇州市',
              '新津县', '邛崃市',
              '金堂县', '大邑县', '简阳市', '蒲江县'],
            axisLabel:{
              interval:0,
              rotate:55,//倾斜度 -90 至 90 默认为0
              margin:15,
              textStyle:{
                color:'#D9E1FF',
                fontSize: 12
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
            min:0,
            max: 3500000,
            splitNumber: 7,
            splitLine: {
              show: true,
              //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED']
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
            name: '',
            type: 'bar',
            itemStyle:{
              normal:{
                color:'#ffc637'
              }
            },
            data: [185410, 2000000, 185410, 185410, 2000000, 298540,36540,298540,36540,
              185410, 2000000, 185410, 185410,
              185410, 2000000, 185410, 2000000, 185410, 185410, 2000000, 298540, 2000000]
          }]
        },
        option2: {
          title: {
            textStyle: {
              color: '#fff',
              fontWeight: 'normal',
            },
            x: 'center',
          },
          tooltip: {
//           position: ['35%','20%'],
            formatter: '{b}<br />{c} %',
            textStyle:{
              fontSize:12
            }
          },
          grid: {
            left:'6%',
            right: '5%',
            top: '30%',
            bottom:'30%'
          },
          xAxis: {
            data: ['龙泉驿区', '高新区', '彭州市', '青羊区', '武侯区', '锦江区', '成华区',
              '金牛区', '新都区', '双流区','温江区', '青白江区', '都江堰市', '郫县','天府新区', '崇州市',
              '新津县', '邛崃市',
              '金堂县', '大邑县', '简阳市', '蒲江县'],
            axisLabel:{
              interval:0,
              rotate:55,//倾斜度 -90 至 90 默认为0
              margin:15,
              textStyle:{
                color:'#D9E1FF',
                fontSize: 12
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
            type:'value',
            min: -40,
            max: 120,
            interval: 20,
//           splitNumber: 7,
            splitLine: {
              show: true,
              //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED']
              },
            },
            axisLine: {
              show: false
            },
            axisLabel: {
              textStyle: {
                color: '#D9E1FF',
              },
              formatter: '{value} %'
            },
          },
          series: [{
            name: '',
            type: 'bar',
            itemStyle:{
              normal:{
                color:'#ffc637'
              }
            },
            data: [100, 99, 88, 111, -30, -20,77, 100, 111, 78, 100, 98, -10, 76, -20,99, 120, 100, -20,99, 120, 100]
          }]
        },
        option3: {
          title: {
            textStyle: {
              color: '#fff',
              fontWeight: 'normal',
            },
            x: 'center',
          },
          color: ['#9d9f10', '#ffc637', '#f87100'],
          legend: {
            top: '12%',
            left: '4%',
            data: [{name: '增值税',icon: 'circle'},{name: '消费税',icon: 'circle'},{name: '所得税',icon: 'circle'}],
            textStyle: {
              color: '#fff'
            }
          },
          tooltip: {
//           position: ['35%','20%'],
            formatter: '{b}<br />{c}',
            textStyle:{
              fontSize: 12
            }
          },
          grid: {
            left:'10%',
            right: '5%',
            top: '30%',
            bottom:'30%'
          },
          xAxis: {
            data: ['龙泉驿区', '高新区', '彭州市', '青羊区', '武侯区', '锦江区', '成华区',
              '金牛区', '新都区', '双流区','温江区', '青白江区', '都江堰市', '郫县','天府新区', '崇州市',
              '新津县', '邛崃市',
              '金堂县', '大邑县', '简阳市', '蒲江县'],
            axisLabel:{
              interval:0,
              rotate:55,//倾斜度 -90 至 90 默认为0
              margin:15,
              textStyle:{
                color:'#D9E1FF',
                fontSize: 12
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
            min:0,
            max: 3500000,
            splitNumber: 7,
            splitLine: {
              show: true,
              //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED']
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
            name: '增值税',
            type: 'bar',
            itemStyle: {

            },
            data: [185410, 2000000, 185410, 185410, 2000000, 298540,36540,298540,36540,
              185410, 2000000, 185410, 185410,
              185410, 2000000, 185410, 2000000, 185410, 185410, 2000000, 298540, 2000000]
          },
            {
              name: '消费税',
              type: 'bar',
              data: [185410, 2000000, 185410, 185410, 2000000, 298540,36540,298540,36540,
                185410, 2000000, 185410, 185410,
                185410, 2000000, 185410, 2000000, 185410, 185410, 2000000, 298540, 2000000]
            },
            {
              name: '所得税',
              type: 'bar',
              data: [185410, 2000000, 185410, 185410, 2000000, 298540,36540,298540,36540,
                185410, 2000000, 185410, 185410,
                185410, 2000000, 185410, 2000000, 185410, 185410, 2000000, 298540, 2000000]
            }
          ]
        },
        option4: {
          title: {
            textStyle: {
              color: '#fff',
              fontWeight: 'normal',
            },
            x: 'center',
          },
          color: ['#9d9f10', '#ffc637', '#f87100'],
          legend: {
            top: '12%',
            left: '4%',
            data: [{name: '增值税',icon: 'circle'},{name: '消费税',icon: 'circle'},{name: '所得税',icon: 'circle'}],
            textStyle: {
              color: '#fff'
            }
          },
          tooltip: {
//           position: ['35%','20%'],
            formatter: '{b}<br />{c} %',
            textStyle:{
              fontSize:12
            }
          },
          grid: {
            left:'6%',
            right: '5%',
            top: '30%',
            bottom:'30%'
          },
          xAxis: {
            data: ['龙泉驿区', '高新区', '彭州市', '青羊区', '武侯区', '锦江区', '成华区',
              '金牛区', '新都区', '双流区','温江区', '青白江区', '都江堰市', '郫县','天府新区', '崇州市',
              '新津县', '邛崃市',
              '金堂县', '大邑县', '简阳市', '蒲江县'],
            axisLabel:{
              interval:0,
              rotate:55,//倾斜度 -90 至 90 默认为0
              margin:15,
              textStyle:{
                color:'#D9E1FF',
                fontSize: 12
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
            type:'value',
            min: -40,
            max: 120,
            interval: 20,
//           splitNumber: 7,
            splitLine: {
              show: true,
              //  改变轴线颜色
              lineStyle: {
                // 使用深浅的间隔色
                color: ['#64B6ED']
              },
            },
            axisLine: {
              show: false
            },
            axisLabel: {
              textStyle: {
                color: '#D9E1FF',
              },
              formatter: '{value} %'
            },
          },
          series: [{
            name: '增值税',
            type: 'bar',
            data: [100, 99, 88, 111, -30, -20,77, 100, 111, 78, 100, 98, -10, 76, -20,99, 120, 100, -20,99, 120, 100]
          },
            {
              name: '消费税',
              type: 'bar',
              data: [100, 99, 88, 111, -30, -20,77, 100, 111, 78, 100, 98, -10, 76, -20,99, 120, 100, -20,99, 120, 100]
            },
            {
              name: '所得税',
              type: 'bar',
              data: [100, 99, 88, 111, -30, -20,77, 100, 111, 78, 100, 98, -10, 76, -20,99, 120, 100, -20,99, 120, 100]
            }
          ]
        },
      }
    },
    mounted: function () {
      var self = this;
      setTimeout(function () {
        self.dataInit(1);
      },300)
    },
    methods: {
      dataInit: function (i) {
        var echarts =  this.echarts.init(document.getElementById('component_chart'));
        echarts.clear();
        echarts.setOption(this['option' + i]);
      }
      ,handlerClick: function (index) {
        //tab 切换
        var self  = this;
        this.tab.forEach(function (el,i,arr) {
          if(index === i && arr[index] !== true){
            arr[index].state = true;
          }else {
            arr[i].state = false;
          }
        });

        switch (index){
          case 0:
            self.dataInit(1);
            break;
          case 1:
            self.dataInit(2);
            break;
          case 2:
            self.dataInit(3);
            break;
          case 3:
            self.dataInit(4);
            break;
          default:
            return;
        }
      }
    }
  }
</script>
<style scoped="">
  .component__box{
    position: relative;
    /*padding: 20px;*/
    width: 100%;
    height: 100%;
  }
  .component__chart{
    width: 100%;
    height: 100%;
  }
  .chart__title{
    position: absolute;
    left: 0;
    right: 0;
    z-index: 99;
    text-align: center;
    color: #fff;
  }

  .tab__charts{
    position: absolute;
    left: 45%;
    right: 0;
    z-index: 99;
    top: 40px;
    height: 40px;
    line-height: 40px;
  }
  .tab__charts li{
    display: inline-block;
    width: 100px;
    text-align: center;
    margin-left: 20px;
    font-size: 12px;
    color: #b9bad5;
    cursor: pointer;
    background-image: url("../../../../assets/images/tkbot.png");
    background-repeat: no-repeat;
    background-size: cover;
  }
  .tab__charts li.active{
    color: #fff;
    background-image: url("../../../../assets/images/tkselectbot.png");
  }
</style>
