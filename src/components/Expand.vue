<template>
  <div>
    <div class="recommand-playlist">{{title}}</div>
    <img src="/static/icon/playlistNext.png" style="width: 20px;height: 20px;float: right;margin-top: -32px;margin-right: 10px">
  </div>
</template>

<script>
    export default {
        name: "Expand.vue",
      props: ['title']
    }
</script>

<style scoped>
  .recommand-playlist {
    width: 100%;
    height:40px;
    text-align:center;
    margin-top: 20px;
    font-size: 18px;
    letter-spacing:10px;
    z-index: 10000;
  }
</style>
