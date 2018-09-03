<template>
  <div class="navbar">
    <div style="display: flex;padding-top: 10px">
      <div style="flex: 1;text-align: center" v-on:click="$emit('showSiderDetail')"><img src="/static/icon/menu.png" mode="scaleToFill" class="menu-icon"/></div>
      <div style="flex: 4;display: flex">
        <div class="navbar-item">我的</div>
        <div class="navbar-item">音乐馆</div>
        <div class="navbar-item">发现</div>
      </div>
      <div style="flex: 1;text-align: center"><img mode='scaleToFill' src="/static/icon/add.png" class="add-icon"></div>
    </div>
  </div>
</template>

<script>
  import "../../static/weui/weui.css"

  export default {
    props: [],
    data: {
      idx: "我的",
      tabs: ["我的", "音乐馆", "发现"],
      activeIndex: 1,
      sliderOffset: 0,
      sliderLeft: 0,
      sliderWidth: 96,
      src: 'http://img1.3lian.com/2015/w7/85/d/101.jpg',
      showSiderDetail: true
    },
    onLoad: function () {
    },
    components: {
    },
    methods: {
      expandCate: function () {

      }
    }
  }
</script>

<style>
  @import "../../static/weui/weui.css";

  .navbar {
    top: 0px;
    width: 100%;
    text-align: center;
  }
  .navbar-item {
    color: aliceblue;
    font-size: 20px;
    text-align: center;
    flex: 1;
  }
  .navbar-item-on {

  }
  .menu-icon {
    width: 22px;
    height: 22px;
  }
  .add-icon {
    width: 22px;
    height: 22px;
  }
</style>
