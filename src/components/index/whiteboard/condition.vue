<template>
  <div >
    <div id="allback" class="allback">
      <span class="mr10">区域</span>
      <Dropdown class="dropdown" style="line-height: 22px;color: #fff">
        <a href="javascript:void(0)" style="color: #fff;">
          全成都
          <Icon type="arrow-down-b" style="margin-left: 3px;"></Icon>
        </a>
        <DropdownMenu slot="list" style="text-align: center;">
          <DropdownItem>全成都</DropdownItem>
          <DropdownItem>龙泉驿区</DropdownItem>
          <DropdownItem>高新区</DropdownItem>
          <DropdownItem>彭州市</DropdownItem>
          <DropdownItem>青羊区</DropdownItem>
        </DropdownMenu>
      </Dropdown>
      <span class="ml30 mr10">行业</span>
      <Dropdown class="dropdown" style="line-height: 22px;color: #fff">
        <a href="javascript:void(0)" style="color: #fff;">
          电力、热力、燃气及水生产和供应业
          <Icon type="arrow-down-b" style="margin-left: 3px;"></Icon>
        </a>
        <DropdownMenu slot="list" style="text-align: center;">
          <p class="catck">
            <input type="text" class="saerch" placeholder="请输入企业名称">
            <i class="iconfont icon-iconfontzhizuobiaozhun22"></i>
          </p>
          <DropdownItem>电力、热力、燃气及水生产和供应业</DropdownItem>
          <DropdownItem>龙泉驿区</DropdownItem>
          <DropdownItem>高新区</DropdownItem>
          <DropdownItem>彭州市</DropdownItem>
          <DropdownItem>青羊区</DropdownItem>
        </DropdownMenu>
      </Dropdown>
      <span class="ml30 mr10">时间起</span>
      <DatePicker class="datapack" type="date" placeholder="请选择日期" style="width: 150px;color: black"></DatePicker>
      <span class="ml30 mr10">止</span>
      <DatePicker class="datapack" type="date" placeholder="请选择日期" style="width: 150px;color: black"></DatePicker>
      <button class="btnsesion">查询</button>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue'
  export default {
    name: 'HelloWorld',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        name: "开始"
      }
    },
    mounted: function () {
    },
    methods: {}
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .catck{
    position: relative;
  }
  .catck i{
    position: absolute;
    top:15px;
    right:20px;
  }
  .saerch{
    color: #fff;
    width: 90%;
    background-color: #062963;
    border-radius: 5px;
    border: 0 ;
    padding:5px 10px ;
    margin: 10px;
  }
  .btnsesion {
    background-color: #0855AD;
    border: 1px solid #445FA4;
    line-height: 22px;
    padding: 5px 30px;
    border-radius: 5px;
    color: #fff;
    margin-left: 30px;
  }

  .allback {
    margin-top: 10px;
    padding: 20px;
    height: 100px;
    line-height: 60px;
    color: #fff;
    background-image: url(../../../assets/images/condition.png);
    background-repeat: no-repeat;
    background-size: 100% 100%;
  }

</style>
