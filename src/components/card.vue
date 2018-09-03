<template>
  <div>
    <p class="card">
      {{text}}
      My Journey
    </p>
    <div>
      <button v-on:click="$emit('enlarge-text',0.1)">
        Enlarge text
      </button>
    </div>
  </div>
</template>

<script>
export default {
  el: '#blog-posts-events-demo',
  props: {
    text: String
  },
  postFontSize: 1
}
</script>

<style>
.card {
  /*padding: 10px;*/
}
</style>
