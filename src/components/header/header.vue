<template>
  <div>
    <!--头部-->
    <Row class="headerLeftContent text-center">
      <Col span="9">
      <div class="headerLeft ">
        <span>{{time}}</span>
      </div>
      </Col>
      <Col span="6" class="headerText">
      <img src="../../assets/images/logo.png" alt="">
      <span>成都市国家税务局</span>
      </Col>
      <Col span="9">
      <div class="headerright">
        <span class="name">欢迎你：summer</span>
        <span class="layout cursor"><i class="iconfont icon-icon"></i>退出</span>
      </div>
      </Col>
    </Row>
    <Row style="margin-bottom: 10px;">
      <Col :xs="{ span: 4}" :lg="{ span: 3 }">
      <Dropdown class="dropdown " @on-click="toggle_qk">
        <a href="javascript:void(0)">
          <i class="iconfont icon-kuaijiecaidan"></i>
          {{qk_text}}
          <Icon type="arrow-down-b"></Icon>
        </a>
        <DropdownMenu slot="list" style="text-align: center">
          <DropdownItem v-for="(item,index) in qk_obj" :key="index" :name="item.name">{{item.name}}</DropdownItem>
        </DropdownMenu>
      </Dropdown>
      </Col>
      <Col :xs="{ span: 5, offset: 12 }" :lg="{ span: 3, offset: 16 }" class="hoverMao">
      <a href="javascript:void(0)" class=" colorBlue">
        <i class="verticalMiddl iconfont icon-fanhui"></i>
        <span class="mr40 ml40 " @mouseover="isShow = true">本年</span>
        <i class="verticalMiddl iconfont icon-iconfontzhizuobiaozhun19"></i>
      </a>
      <div class="dropdownList" v-show="isShow">
        <div class="colorBlue cursor" @click="toggle('thisYear')">本年
          <i class="iconfont icon-gouxuan pull-right" v-show="thisYear"></i>
        </div>
        <div class="colorBlue cursor" @click="toggle('lastYear')">去年
          <i class="iconfont icon-gouxuan pull-right" v-show="lastYear"></i>
        </div>
        <div>
          <span class="colorBlue mr10">起</span>
          <DatePicker class="inputDate" type="date" placeholder="起始日期" style="width:80%"></DatePicker>
        </div>
        <div>
          <span class="colorBlue mr10">止</span>
          <DatePicker type="date" class="inputDate" placeholder="结束日期" style="width: 80%"></DatePicker>
        </div>
        <div class="btn__group">
          <button class="btn__item btn__item_confirm">确定</button>
          <button class="btn__item btn__item_cancel" @click="isShow = false">取消</button>
        </div>
      </div>
      </Col>
      <Col :xs="{ span: 3}" :lg="{ span: 2 }" class="right">
      <Dropdown class="dropdown">
        <a href="javascript:void(0)">
          全成都
          <Icon type="arrow-down-b"></Icon>
        </a>
        <DropdownMenu slot="list" style="text-align: center">
          <DropdownItem>全成都</DropdownItem>
          <DropdownItem>龙泉驿区</DropdownItem>
          <DropdownItem>高新区</DropdownItem>
          <DropdownItem>彭州市</DropdownItem>
          <DropdownItem>青羊区</DropdownItem>
        </DropdownMenu>
      </Dropdown>
      </Col>
    </Row>
    <!--第一层页面-->
  </div>
</template>

<script>
  export default {
    name: 'headers',
    data() {
      return {
        now: '', //当前时间
        time: '', // 格式化后的当前时间
        isShow: false, //时间弹框
        thisYear: false,
        lastYear: false,
        qk_obj: [{name: '整体情况'}, {name: '集团情况'},{name: '企业情况'},{name: '数据白板'}],
        qk_text: '整体情况', //情况
      }
    },
    mounted: function () {
      let self = this;
      setInterval(function () {
        self.now = new Date().getTime();
        switch (sessionStorage.getItem("headerJuck")){
          case 'oneflore':
            self.qk_text = '整体情况';
            break;
          case 'twoflore':
            self.qk_text = '集团情况';
            break;
          case 'treenflore':
            self.qk_text = '企业情况';
            break;
          case 'lostFlore':
            self.qk_text = '数据白板';
            break;
        }
      }, 1000);
    },
    methods: {
      //时间弹框
      toggle: function (type) {
        switch (type) {
          case 'thisYear':
            this.thisYear = true;
            this.lastYear = false;
            break;
          case 'lastYear':
            this.thisYear = false;
            this.lastYear = true;
            break;
          default:
            return;
        }
      },
      //情况切换
      toggle_qk: function (name) {
        this.qk_text = name;
        switch (name) {
          case '整体情况':
          this.$emit('headerJuck','oneflore');
            sessionStorage.setItem("headerJuck", 'oneflore');
          break;
          case '集团情况':
            this.$emit('headerJuck','twoflore');
            sessionStorage.setItem("headerJuck", 'twoflore');
            break;
          case '企业情况':
            this.$emit('headerJuck','treenflore');
            sessionStorage.setItem("headerJuck", 'treenflore');
            break;
          case '数据白板':
            this.$emit('headerJuck','lostFlore');
            sessionStorage.setItem("headerJuck", 'lostFlore');
            break;
        }
      }
    },
    watch: {
      //实时时间显示
      now: function () {
        this.time = this.tool.toDateString(this.now, 'yyyy-MM-dd HH:mm:ss');
      }
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .dropdownList {
    /*display: none;*/
    position: absolute;
    z-index: 1000;
    background: #113B85;
    border: 1px solid #445FA4;
    padding: 5px 10px;
    border-radius: 8px;
  }

  .hoverMao:hover div.dropdownList {
    display: block;
  }

  .colorBlue {
    line-height: 38px;
  }

  .headerText img {
    height: 40px;
    margin-right: 18px;
  }

  .headerLeft span {
    color: #67C2F9;
    line-height: 38px;
  }

  .headerText span {
    color: #fff;
    font-size: 20px;
  }

  .headerLeftContent {
    padding: 10px;
  }

  .headerLeft {
    height: 40px;
    background: url(../../assets/images/headleft.png) no-repeat;
    background-size: 80% 100%;
    background-position: 100% 0px;
  }

  .headerright .name {
    margin-right: 15px;
  }

  .headerright .layout {
    margin-left: 10px;
  }

  .headerright > span + span i {
    vertical-align: middle;
    margin-right: 8px;
  }

  .headerright {
    height: 40px;
    background: url(../../assets/images/headright.png) no-repeat;
    background-size: 80% 100%;
    color: #EBECEE;
    line-height: 38px;
  }

  /*btn*/
  .btn__group {
    margin: 10px 0;
  }

  .btn__item {
    width: 64px;
    height: 30px;
    line-height: 30px;
    border-radius: 20px;
    border: 1px solid #405faf;
    margin-left: 5px;
    cursor: pointer;
  }

  .btn__item:hover {
    opacity: 0.8;
  }

  .btn__item_confirm {
    color: #fff;
    background-color: #102667;
  }

  .btn__item_cancel {
    color: #55adea;
    background-color: #1c4a9a;
  }
</style>
