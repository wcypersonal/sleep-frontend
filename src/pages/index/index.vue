<template>
  <div style="text-align: center;min-height: 100%;overflow-y:hidden">
    <!--<siders v-if="showSider" v-on:showSiderDetail="changeSider"></siders>-->
    <siders v-on:showSiderDetail="changeSider"></siders>
    <!--<div>-->
      <!--<div :style="{ fontSize: postFontSize + 'em' }">-->
        <!--<Card :text='Myjourney' v-on:enlarge-text="changeSider"></Card>-->
      <!--</div>-->
    <!--</div>-->
    <!--<div class="sider-on" @click="hideSider"></div>-->
    <scroll-view class="scroll" :style="scollStyle">
      <div>
        <div style="background: #31c37c;height: 80px;">
          <navbar v-on:showSiderDetail="changeSider"></navbar>
          <div class="search">
            <div style="display: flex;text-align: center">
              <!--<icon type="search" size="18" color="white" class="search-icon"></icon>-->
              <input placeholder="搜索" color="white"/>
            </div>
          </div>
        </div>
        <swiper indicator-dots="true" autoplay="true" indicator-active-color="white" :interval="5000" :duration="1000" circular = "false">
          <block v-for="(item,index) in imgUrls" :key="index">
            <swiper-item>
              <img :src="item" class="img-item">
            </swiper-item>
          </block>
        </swiper>
        <div class="category">
          <div class="cate-item">
            <img src="/static/icon/singer.png" style="width: 30px;height: 30px"/>
            <div>歌手</div>
          </div>
          <div class="cate-item">
            <img src="/static/icon/rank.png" style="width: 30px;height: 30px"/>
            <div>排行</div>
          </div>
          <div class="cate-item">
            <img src="/static/icon/category.png" style="width: 30px;height: 30px"/>
            <div>分类歌单</div>
          </div>
          <div class="cate-item">
            <img src="/static/icon/radio.png" style="width: 30px;height: 30px"/>
            <div>电台</div>
          </div>
          <div class="cate-item">
            <img src="/static/icon/video.png" style="width: 30px;height: 30px"/>
            <div>视频</div>
          </div>
        </div>
        <div class="recommand">
          <div class="radio">
            <img class="radio-img" src="http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg" style="height: 100px;width: 100px"/>
            <div class="radio-img-second" style="width: 90px;height: 90px"></div>
            <div class="radio-img-third" style="width: 80px;height: 80px"></div>
            <div class="radio-play">
              <img src="/static/icon/recommand.png" style="width: 20px;height: 20px;">
            </div>
            <div class="radio-cover"></div>
            <div class="radio-text"><div style="width: 90px;">个性电台</div></div>
            <!--<div class="radio-text"><div>个性电台</div></div>-->
          </div>
          <div class="digital">
            <div class="digital-item">
              <div class="digital-item-text">
                <div class="digital-item-text-title">新歌新碟</div>
                <div class="digital-item-text-content">华晨宇傲骨唱响斗破..</div>
              </div>
              <div style="flex: 1;" class="digital-img">
                <img src='http://img1.3lian.com/2015/w7/85/d/101.jpg' style="width: 40px;height: 40px;float: right;">
              </div>
            </div>
            <div style="margin-top: 8px" class="digital-item">
              <div class="digital-item-text">
                <div class="digital-item-text-title">数字专辑·票务</div>
                <div class="digital-item-text-content">歌手王凯的音乐告白</div>
              </div>
              <div class="digital-img">
                <img src='http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg' style="width: 40px;height: 40px;float: right;">
              </div>
            </div>
          </div>
        </div>
        <Expand :title="recommandFirst"></Expand>
        <Sixrecommand :authorA="motto" :imgArray="recommandList" :titleArray="recommandTitle"
                      :authorArray="recommandAuthor" :numberArray="recommandNumber"></Sixrecommand>
      </div>
    </scroll-view>
    <div class="sider-on"></div>
    <div class="audio">
      <!--<audio poster='http://y.gtimg.cn/music/photo_new/T002R300x300M000003rsKF44GyaSk.jpg?max_age=2592000' name="此时此刻" id="myAudio"-->
      <!--author="许巍" src='http://ws.stream.qqmusic.qq.com/M500001VfvsJ21xFqb.mp3?guid=ffffffff82def4af4b12b3cd9337d5e7&uin=346897220&vkey=6292F51E1E384E06DCBDC9AB7C49FD713D632D313AC4858BACB8DDD29067D3C601481D36E62053BF8DFEAF74C0A5CCFADD6471160CAF3E6A&fromtag=46'-->
      <!--controls loop></audio>-->
      <div style="line-height: 80px;margin-left: 10px">
        <img src="http://y.gtimg.cn/music/photo_new/T002R300x300M000003rsKF44GyaSk.jpg?max_age=2592000" style="width:40px;height: 40px;border-radius: 20px;border:1px solid">
      </div>
      <div style="margin-left: 15px;margin-top: 6px">
        <div style="text-align: left;font-size: 15px">此时此刻</div>
        <div style="text-align: left;color:#acacac;font-size:12px">许巍</div>
      </div>
      <div style="margin-left: 110px;">
        <canvas canvas-id="playRate" style="width: 30px;height: 30px;"></canvas>
      </div>
      <div style="line-height: 70px;float:right;margin-left: 10px">
        <img src="/static/icon/musicList.png" style="width: 30px;height: 30px"/>
      </div>
    </div>
  </div>
</template>

<script>
  import navbar from "../../components/navbar"
  import Card from "../../components/card";
  import Sixrecommand from "../../components/Sixrecommand"
  import Expand from "../../components/Expand"
  import siders from "../../components/siders"

  export default {
    data () {
      return {
        motto: 'Hello World',
        userInfo: {},
        postFontSize: 2,
        imgUrls: [
          'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg',
          'http://img1.3lian.com/2015/w7/85/d/101.jpg',
          'http://y.gtimg.cn/music/photo_new/T002R300x300M000003rsKF44GyaSk.jpg?max_age=2592000'
        ],
        screenHeight: 2000,
        windowHeight: 2000,
        scollStyle: 'height: 800px;',
        // author: 'testautjor',
        recommandFirst: '为你推荐歌单',
        recommandList: [
          'http://img02.tooopen.com/images/20150928/tooopen_sy_143912755726.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175833047715.jpg',
          'http://img1.3lian.com/2015/w7/85/d/101.jpg',
          'http://y.gtimg.cn/music/photo_new/T002R300x300M000003rsKF44GyaSk.jpg?max_age=2592000',
          'http://img06.tooopen.com/images/20160818/tooopen_sy_175866434296.jpg',
        ],
        recommandTitle: [
          // '金志文','One in A Million','灵魂走在大街上','无常春秋','乌托邦','中国新说唱 第7期'
          '今日推荐歌曲','在这些歌的弹幕里表白','「华语流行」那些适合女生唱的歌','八组归来，少女心爆棚','分手必去KTV唱这些歌曲（男声版）','Michael Jackson-Top Tracks'
        ],
        recommandAuthor: [
          // '金志文','Matoma','韩红','无常春秋','周柏豪','中国新说唱'
          '','','','','',''
        ],
        recommandNumber: [
          '578万','225万','77万','159万','38万'
        ],
        showSider: false
    }
  },

  components: {
    Card,
    navbar,
    Sixrecommand,
    Expand,
    siders
  },

  methods: {
      playRate: function () {
        var context = wx.createCanvasContext('playRate')
        context.setFillStyle('red')
        context.fillRect(10,10,150,75)
        context.draw()


        // context.setStrokeStyle("#00ff00")
        // context.setLineWidth(5)
        // context.rect(0, 0, 200, 200)
        // context.stroke()
        // context.setStrokeStyle("#ff0000")
        // context.setLineWidth(2)
        // context.moveTo(160, 100)
        // context.arc(100, 100, 60, 0, 2 * Math.PI, true)
        // context.moveTo(140, 100)
        // context.arc(100, 100, 40, 0, Math.PI, false)
        // context.moveTo(85, 80)
        // context.arc(80, 80, 5, 0, 2 * Math.PI, true)
        // context.moveTo(125, 80)
        // context.arc(120, 80, 5, 0, 2 * Math.PI, true)
        // context.stroke()
        context.draw()
        console.log('test')
      },
    changeSider: function (enlargeAmount) {
      let that = this
      that.showSider = true
    },
    hideSider: function () {
      let that = this
      if (that.showSider) {
        console.log(that.showSider)
        that.showSider = false
      }
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
    // this.getUserInfo()
    let that = this
    that.playRate()
    wx.getSystemInfo({
      success: function (res) {
        that.screenHeight = res.screenHeight
        that.windowHeight = res.windowHeight
      }
    })
    console.log(that.screenHeight)
    console.log(that.windowHeight)
  },
    onReady: function () {
      // let that = this
      // that.list = this.selectComponent('#listA')
    }
}
</script>

<style scoped>
  .scroll {
    /*overflow: auto;*/
    overflow-y: scroll;
    scroll-y: true
    /*height: 504px;*/
  }
  /*.icon {*/
    /*color: #32c27c;*/
  /*}*/
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
  .img-item {
    height: 200px;
    width: 100%;
  }
  .search {
    opacity: 0.8;
    margin: 10px;
    border: 1px solid transparent;
    background: #2daf71;
    color:white;
    text-align: center;
  }
  .search-icon {
    left: 50px;
    margin-top: 2px;
    /*z-index: 2;*/
    margin-left: 10px;
    position: absolute;
  }
.sider-on {
  z-index: 100;
  position:relative;
  background: black;
  opacity: 0.3;
  /*opacity: 0.4;*/
  width: 100%;
  height: 1000px;
}
  .category {
    /*border: 2px solid #888888;*/
    width: 94%;
    height: 90px;
    margin-left: 3%;
    margin-top: -8px;
    background: white;
    display: flex;
    z-index: 1;
    position: relative;
    box-shadow: 2px 2px 2px 2px #d5d5d6;
  }

  .cate-item {
    flex: 1;
    font-size: 16px;
    margin-top: 10px;
  }
  .recommand {
    /*background: #586c94;*/
    text-align: center;
    display: flex;
    width: 94%;
    margin-left: 3%;
    height: 100px;
    margin-top: 20px;
  }
  .radio {
    flex: 2;
    display: flex;
    text-align: center;
  }
  .radio-text {
    z-index:6;
    color: white;
    font-size: 15px;
    margin-top: 70px;
    text-align: center;
  }
  .radio-play {
    width: 105px;
    z-index: 5;
    position: absolute;
    text-align: center;
    line-height: 105px;
  }
  .radio-cover {
    width: 105px;
    height: 105px;
    background: black;
    opacity: 0.3;
    z-index: 4;
    position:absolute;
  }
  .radio-img {
    position:absolute;
    z-index: 3;
    opacity: 0.8;
    /*margin-left: 10px;*/
  }
  .radio-img-second {
    position:absolute;
    z-index: 2;
    background: #c8c8cd;
    left: 28px;
    margin-top:5px;
    opacity: 0.8;
  }
  .radio-img-third {
    position:absolute;
    z-index: 1;
    background: #efeff4;
    left: 42px;
    margin-top: 10px;
    opacity: 0.8;
  }
  .digital {
    flex: 3;
    /*background: #e64340;*/
    flex-direction: column;
    /*display: flex;*/
    height:100px;
  }

  .digital-item {
    display: flex;
    background: #f5f5f5;
    height:50px;
  }
  .digital-item-text {
    flex: 2;
    flex-direction: column;
    display: flex;
    margin-left: 8px;
    margin-top: 3px;
  }
  .digital-item-text-title {
    flex:1;
    font-size: 15px;
    text-align: left
  }
  .digital-item-text-content {
    flex: 1;
    font-size: 12px;
    color: #acacac;
    text-align: left
  }
  .digital-img {
    flex: 1;
  }
  .recommand-playlist {
    width: 100%;
    height:40px;
    text-align:center;
    margin-top: 20px;
    font-size: 18px;
    letter-spacing:10px
  }
  .playlist {
    /*margin-left: 3%;*/
    display: flex;
    width: 100%;
  }
  .playlist-item {
    flex: 1;
    margin-top: 3px;
  }
  .audio {
    width: 100%;
    background: white;
    height: 60px;
    position: fixed;
    bottom: 0;
    border: 1px solid #f5f5f5;
    display: flex;
    z-index: 99;
  }
</style>
