<template>
  <div class="player" ref="player"></div>
</template>

<script>
import DPlayer from "dplayer";
export default {
  name: "Player",
  mounted: function() {
    const dp = new DPlayer({
      container: this.$refs.player,
      screenshot: true,
      lang: "zh-cn",
      volume: 1,
      autoplay: true,
      loop: true,
      video: {
        url: this.url,
        pic: "./影 流 之 主.jpg"
      }
    });
    this.dp = dp;
  },

  watch: {
    // 如果 `question` 发生改变，这个函数就会运行
    url: function(newQuestion, oldQuestion) {
      console.log(newQuestion);
      this.dp.switchVideo({
        url: newQuestion
      });
    }
  },
  data: function() {
    return {
      trueurl: this.url,
      dp: {}
    };
  },
  props: {
    url: String
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
