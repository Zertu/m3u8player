<template>
  <div id="app">
    <Player :url="url" />
    <el-input v-model="temp">
      <template slot="append">
        <i @click="play" class="el-icon-caret-right"></i>
      </template>
    </el-input>
  </div>
</template>

<script>
import Player from "./components/Player.vue";
import "dplayer/dist/DPlayer.min.css";

export default {
  name: "app",
  components: {
    Player
  },
  methods: {
    play: function() {
      // `this` 在方法里指向当前 Vue 实例
      console.log(this);
      this.url = this.temp;
    }
  },
  data: function() {
    return {
      url: "./影 流 之 主.flv",
      temp: "./影 流 之 主.flv"
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
