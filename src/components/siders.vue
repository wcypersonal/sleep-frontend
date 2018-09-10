<template>
    <div class="sider">
      <div class="message" id="message">
        <div class="message-item">
          <div class="sider-personal-left">个性装扮</div>
          <div class="sider-personal-right">默认套装</div>
        </div>
        <div class="message-item">
          <div class="sider-personal-left">消息中心</div>
          <!--<div class="sider-personal-right">默认套装</div>-->
        </div>
        <div class="message-item">
          <div class="sider-personal-left">免流量服务</div>
          <div class="sider-personal-right">red</div>
        </div>
      </div>
      <div class="timer" id="timer">
        <div class="timer-item">
          <div class="timer-item-left">定时关闭</div>
          <div class="timer-item-right">

          </div>
        </div>
        <div class="timer-item">
          <div class="timer-item-left">仅Wi-Fi联网</div>
          <div class="timer-item-right">

          </div>
        </div>
        <div class="timer-item">
          <div class="timer-item-left">流量提醒</div>
          <div class="timer-item-right">
            testffg;glaksdnglaksngl;kr
          </div>
        </div>
        <div class="timer-item">
          <div class="timer-item-left">听歌偏好</div>
        </div>
      </div>
      <div class="split"></div>
      <div class="setting">
        <div class="setting-item">
          <div class="setting-item-context">设置</div>
          <div class="setting-item-img">
            <image src="../../static/icon/setting.png" style="width: 18px;height: 18px;"/>
          </div>
        </div>
        <div class="setting-item">
          <div class="setting-item-context">退出登录/关闭</div>
          <div class="setting-item-img">
            <image src="../../static/icon/logout.png" style="width: 18px;height: 18px;"></image>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
      name: "sider.vue",
      data: function () {
        return {

        }
      },
      created () {
      }
    }
</script>

<style scoped>
  .sider {
    border-width: 0 1px 0 0;
    border-style: solid;
    border-color: #c8c8cd;
    float: left;
    width: 300px;
    height: 2000px;
    background: white;
    z-index: 1000;
    margin-top: 0px;
    position:absolute;
    /*flex-direction: column;*/
    text-align: center;
    align: center;
    /*background: #c8c8cd;*/
  }
  .sider-personal-left {
    display: inline-block;
    /*background: #52a341;*/
    left: 20px;
    position: absolute;
    font-size: 18px;
  }
  .sider-personal-right {
    display: inline-block;
    position: absolute;
    /*background: #586c94;*/
    right: 20px;
    color: #c8c8cd;
    font-size: 16px;
  }
  .sider-content {
    width: 80%;
    /*margin: 20px;*/
    background: #e64340;
    display: inline-block;
  }
  .message {
    margin-top: 30px;
    flex-direction: column;
    display: flex;
    height: 110px;
    /*background: #e64340;*/
    /*margin-left: 40px;*/
  }
  .message-item {
    /*background: #52a341;*/
    flex: 1;
    display: flex;
    line-height: inherit;
    /*margin-top: 5px;*/
    /*font-size: 18px;*/
    /*float: left;*/
    /*position: absolute;*/
  }
  .timer {
    margin-top: 30px;
    flex-direction: column;
    display: flex;
    height: 147px;
    margin-left: 20px;
    font-size: 17px;
  }
  .timer-item {
    flex:1;
    display: flex;
    line-height: inherit;
  }
  .timer-item-left {

  }
  .timer-item-right {
    position: absolute;
    float: right;
    margin-right: 10px;
  }
  .split {
    background: #d5d5d6;
    height: 3px;
    width: 260px;
    margin-left: 20px;
    position: fixed;
    bottom: 50px;
  }
  .setting {
    position: fixed;
    bottom:0;
    height:45px;
    width: 300px;
    /*background: #52a341;*/
    display: flex;
  }
  .setting-item {
    flex: 1;
    /*display: inline-block;*/
    height: 45px;
    line-height: 45px;
    /*display: table-cell;*/
    /*vertical-align: middle;*/
    margin: auto;
  }
  .setting-item-img {
    /*display: inline-block;*/
    position: absolute;
    float: left;
    margin-left: 18px;
    width: 20px;
    height: 45px;
    line-height: 45px;
  }
  .setting-item-context {
    /*display: inline-block;*/
    position: absolute;
    float: left;
    margin-left: 40px;
    font-size: 17px;
    line-height: 45px;
    /*height: 20px;*/
    /*margin-left: 10px;*/
  }
</style>
