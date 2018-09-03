<template>
  <div>
    <div style="width: 100%;" class="playlist">
      <div class="playlist-item">
        <div style="text-align: center">
          <div class="playlist-cover-first"></div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <div class="playlist-cover-grid"></div>
          <div class="playlist-cover-grid-month">∙八月∙</div>
          <div class="playlist-cover-grid-date">29</div>
          <img :src="imgArray[0]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[0]}}</div>
          <div class="playlist-text-content">{{authorArray[0]}}</div>
        </div>
      </div>
      <div class="playlist-item">
        <div>
          <div class="playlist-cover-other"></div>
          <img src="/static/icon/beats.png" class="playlist-cover-icon" style="margin-left: 5px">
          <div class="playlist-cover-text">{{numberArray[0]}}</div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <img :src="imgArray[1]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[1]}}</div>
          <div class="playlist-text-content">{{authorArray[1]}}</div>
        </div>
      </div>
      <div class="playlist-item">
        <div>
          <div class="playlist-cover-other"></div>
          <img src="/static/icon/beats.png" class="playlist-cover-icon" style="margin-left: 5px">
          <div class="playlist-cover-text">{{numberArray[1]}}</div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <img :src="imgArray[2]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[2]}}</div>
          <div class="playlist-text-content">{{authorArray[2]}}</div>
        </div>
      </div>
    </div>
    <div style="width: 100%" class="playlist">
      <div class="playlist-item">
        <div>
          <div class="playlist-cover-other"></div>
          <img src="/static/icon/beats.png" class="playlist-cover-icon" style="margin-left: 5px">
          <div class="playlist-cover-text">{{numberArray[2]}}</div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <img :src="imgArray[3]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[3]}}</div>
          <div class="playlist-text-content">{{authorArray[3]}}</div>
        </div>
      </div>
      <div class="playlist-item">
        <div>
          <div class="playlist-cover-other"></div>
          <img src="/static/icon/beats.png" class="playlist-cover-icon" style="margin-left: 5px">
          <div class="playlist-cover-text">{{numberArray[3]}}</div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <img :src="imgArray[4]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[4]}}</div>
          <div class="playlist-text-content">{{authorArray[4]}}</div>
        </div>
      </div>
      <div class="playlist-item">
        <div>
          <div class="playlist-cover-other"></div>
          <img src="/static/icon/beats.png" class="playlist-cover-icon" style="margin-left: 5px">
          <div class="playlist-cover-text">{{numberArray[4]}}</div>
          <img src="/static/icon/recommandplay.png" class="playlist-cover-icon" style="margin-left: 80px">
          <img :src="imgArray[5]" class="playlist-img">
        </div>
        <div class="playlist-text">
          <div class="playlist-text-title">{{titleArray[5]}}</div>
          <div class="playlist-text-content">{{authorArray[5]}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
    export default {
      name: "Sixrecommand.vue",
      props: {
        authorA: String,
        imgArray: Array,
        titleArray: Array,
        authorArray: Array,
        numberArray: Array
      },
      data: {
      },
      methods: function () {

      },
      created() {
        // console.log(this.imgArray)
      }
    }
</script>

<style scoped>
  .playlist {
    /*margin-left: 3%;*/
    display: flex;
    width: 100%;
  }
  .playlist-item {
    flex: 1;
    margin-top: 3px;
  }
  .playlist-cover-first {
    z-index: 2;
    width: 110px;
    height: 110px;
    opacity: 0.4;
    background: black;
    display: flex;
    position:absolute;
    margin-left: 10px;
  }
  .playlist-cover-grid {
    border: 2px solid white;
    width: 60px;
    height: 60px;
    line-height: 110px;
    margin-top: 25px;
    margin-left: 35px;
    position: absolute;
    z-index: 4;
  }
  .playlist-cover-grid-month {
    text-align: center;
    /*width: 50px;*/
    letter-spacing: 3px;
    font-size: 14px;
    color: white;
    z-index: 4;
    width: 60px;
    position: absolute;
    margin-left: 35px;
    margin-top: 30px;
  }
  .playlist-cover-grid-date {
    text-align: center;
    /*width: 50px;*/
    letter-spacing: 3px;
    font-size: 30px;
    color: white;
    z-index: 4;
    position: absolute;
    margin-left: 35px;
    margin-top: 47px;
    letter-spacing: 5px;
    width: 60px;
  }
  .playlist-cover-other {
    z-index: 2;
    width: 110px;
    height: 110px;
    opacity: 0.4;
    background: black;
    display: flex;
    position:absolute;
    margin-left: 10px;
  }
  .playlist-cover-icon {
    height: 20px;
    width: 20px;
    z-index: 5;
    position:absolute;
    margin-top: 85px;
    color:white;
    font-size: 14px;
  }
  .playlist-cover-text {
    height: 20px;
    /*width: 20px;*/
    z-index: 3;
    position:absolute;
    margin-top: 86px;
    color:white;
    font-size: 14px;
    line-height: 20px;
    margin-left: 35px;
  }
  .playlist-img {
    width: 110px;
    height: 110px;
    z-index: 1;
  }
  .playlist-text {
    text-align: left;
    margin-left: 15px;
    margin-top: 0px
  }
  .playlist-text-title {
    font-size: 12px;
    color: black;
    text-align: left
  }
  .playlist-text-content {
    font-size: 12px;
    color: #acacac;
    text-align: left
  }
</style>
