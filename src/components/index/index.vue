<template>
  <div class="indexback">
    <!--头部-->
    <v-userheader v-on:headerJuck="juckFuncion"></v-userheader>
    <!--第一层页面-->
    <Row v-if="juck == 'oneflore'">
      <Row class=" flourOne">
        <Col span="7" >
        <v-qhqyzb></v-qhqyzb>
        </Col>
        <Col span="10">
        <v-map></v-map>
        </Col>
        <Col span="7">
        <v-gzzbqk></v-gzzbqk>
        </Col>
      </Row>
      <Row class="cf">
        <Col span="7" style="height: 500px">
        <v-qsqy></v-qsqy>
        </Col>
        <Col span="10" >
        <v-allback v-show="false"></v-allback>
        <v-income></v-income>
        <v-tenprogress></v-tenprogress>
        </Col>
        <Col span="7" >
        <v-qshy></v-qshy>
        </Col>
      </Row>
    </Row>
    <!--第二层页面-->
    <Row >
      <Row v-if="serchShow">
        <Col span="24" class="text-center">
        <input type="text" class="textplace" placeholder="请输入集团名字">
        </Col>
      </Row>
      <!--集团情况-->
      <Row  class="mt30" v-if="juck == 'twoflore'">
        <Row>
          <Col span="24" style="height:125px;">
            <v-jtqktotal></v-jtqktotal>
          </Col>
        </Row>
        <Row class="mt20" :gutter="16">
          <Col span="12" style="height:350px;">
          <v-qyfb></v-qyfb>
          </Col>
          <Col span="12" style="height:350px;">
          <v-hyfb></v-hyfb>
          </Col>
        </Row>
        <Row class="mt20" style="background-color: #093a72">
          <Col span="6" style="height:300px;">
          <v-gzzbqks></v-gzzbqks>
          </Col>
          <Col span="9" style="height:300px;">
          <v-szsssrbh></v-szsssrbh>
          </Col>
          <Col span="9" style="height:300px;">
          <v-sztbbh></v-sztbbh>
          </Col>
        </Row>
        <Row class="mt20">
          <Col span="24" style="height:100%">
          <v-jtcyqy></v-jtcyqy>
          </Col>
        </Row>
      </Row>
      <!--企业情况-->
      <Row v-if="juck == 'treenflore'" class="mt30">
        <Row :gutter="16">
          <Col span="12" style="height: 280px">
            <v-qyjbxx></v-qyjbxx>
          </Col>
          <Col span="12" style="height: 280px">
          <v-qyszzb></v-qyszzb>
          </Col>
        </Row>
        <Row class="mt20 qyqk__line-box" >
          <Col span="12" style="height: 300px">
          <v-qyszsssrybh></v-qyszsssrybh>
          </Col>
          <Col span="12" style="height: 300px">
          <v-qysztbbh></v-qysztbbh>
          </Col>
        </Row>
        <Row class="mt20">
          <Col span="24" style="height:500px;">
            <v-tablemk></v-tablemk>
          </Col>
        </Row>
      </Row>
    </Row>
    <!--第三层页面-->
    <Row v-if="juck == 'lostFlore'">
      <Row>
        <Col span="24"><v-condition></v-condition></Col>
      </Row>
      <Row class="mt20">
        <v-Pie></v-Pie>
      </Row>
      <Row class="mt20">
        <v-line></v-line>
      </Row>
    </Row>
  </div>
</template>

<script>
  import Header from '../header/header.vue'
  import Qhqyzb from './allindex/qhqyzb/Qhqyzb.vue'
  import income from './allindex/income/income.vue'
  import map from './allindex/map/cdMap.vue'
  import allback from './allindex/income/allback.vue'
  import tenprogress from './allindex/income/tenprogress.vue'
  import qshy from './allindex/qshy/qshy.vue'
  import gzzbqk from './allindex/gzzbqk/gzzbqk.vue'
  import gzzbqks from './jtqk/gzzbqk/gzzbqks.vue'
  import Qsqy from './allindex/qsqy/Qsqy.vue'
  import qyfb from './jtqk/qyfb/qyfb.vue'
  import hyfb from './jtqk/hyfb/hyfb.vue'
  import szsssrbh from './jtqk/szsssrbh/szsssrbh.vue'
  import sztbbh from './jtqk/sztbbh/sztbbh.vue'
  import jtqkTotal from  './jtqk/jtqkTotal/jtqkTotal.vue'
  import qyjbxx from './qyqk/qyjbxx/qyjbxx.vue'
  import qyszzb from './qyqk/qyszzb/qyszzb.vue'
  import VQyszzb from "./qyqk/qyszzb/qyszzb.vue";
  import qyszsssrybh from "./qyqk/qyszsssrybh/qyszsssrybh.vue"
  import VQyszsssrybh from "./qyqk/qyszsssrybh/qyszsssrybh"
  import qysztbbh from "./qyqk/qysztbbh/qysztbbh.vue"
  import VQysztbbh from "./qyqk/qysztbbh/qysztbbh";
  import condition from "./whiteboard/condition";
  import Pie from "./whiteboard/Pie";
  import line from "./whiteboard/line";
  import jtcyqy from  './jtqk/jtcyqy/jtcyqy.vue'
  import Tablemk from './qyqk/tablemk/Tablemk.vue'
  export default {
    name: 'index',
    data () {
      return {
        juck:'oneflore',
        serchShow:false
      }
    },
    watch:{
      juck:function(){
        this.juck = sessionStorage.getItem("headerJuck");
        this.serchShow = this.juck == 'oneflore'||'lostFlore'?false:true;
      }
    },
    mounted: function () {
      let self = this;
      this.$nextTick(function () {
        let juck = sessionStorage.getItem("headerJuck");
        if(juck){
          this.juck = juck;
        }
      })
    },
    methods:{
      juckFuncion(res){
        this.juck = res;
      }
    },
    components:{
      'v-userheader':Header,
      'v-income':income,
      'v-allback': allback,
      'v-gzzbqk':gzzbqk,
      'v-gzzbqks':gzzbqks,
      'v-qhqyzb': Qhqyzb,
      'v-qsqy': Qsqy,
      'v-tenprogress':tenprogress,
      'v-qshy': qshy,
      'v-map':map,
      'v-qyfb':qyfb,
      'v-hyfb':hyfb,
      'v-szsssrbh':szsssrbh,
      'v-sztbbh':sztbbh,
      'v-jtqktotal':jtqkTotal,
      'v-jtcyqy':jtcyqy,
      'v-qyjbxx': qyjbxx,
      'v-qyszzb': qyszzb,
      'v-qyszsssrybh': qyszsssrybh,
      'v-qysztbbh':qysztbbh,
      'v-condition':condition,
      'v-Pie':Pie,
      'v-line':line,
      'v-tablemk': Tablemk
    }
  }
</script>
<style scoped>
  .textplace{
    color: #fff;
    background: #11135D;
    width: 40%;
    border-radius: 10px;
    border: none;
    padding: 10px 15px;
    height:30px;
  }
  .flourOne div{
    height:250px;
  }
  .indexback{
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right:0;
    padding: 10px 20px;
    overflow-y: scroll;
    background-image: url(../../assets/images/back.png);
    background-size:100% 100%;
  }
  .cf{
    margin: 12px 0;
  }
  .qyqk__line-box{
    background-image: url('../../assets/images/box_hsline.png'),
    url('../../assets/images/box_hsline.png'),
    url('../../assets/images/box_ssline.png'),
    url('../../assets/images/box_ssline.png');
    background-repeat: no-repeat;
    background-position: top center,bottom center,left center, right center;
    background-origin: padding-box;
    background-size: 98% 4px, 98% 4px,auto 98%,auto 98%;
  }
</style>
