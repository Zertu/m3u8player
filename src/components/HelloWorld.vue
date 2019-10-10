<template>
  <div class="player" ref="player"></div>
</template>

<script>
import DPlayer from "dplayer";
export default {
  name: "HelloWorld",
  mounted: function() {
    console.log(this.$refs);
    const dp = new DPlayer({
      container: this.$refs.player,
      screenshot: true,
      video: {
        url: "./影 流 之 主.flv",
        pic: "./影 流 之 主.jpg"
      }
    });
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.player {
  widows: 800px;
  height: 600px;
}
</style>
