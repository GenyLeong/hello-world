<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <Packchart :tweetData="loadData" />
  </div>
</template>

<script>
/* eslint-disable */
/* import HelloWorld from "./components/HelloWorld.vue"; */
import PackChart from "./components/Chart.vue";

import * as d3 from "d3";

export default {
  name: "app",
  components: {
    PackChart
  },
  data: function() {
    return {
      loadData: []
    };
  },
  mounted() {
    console.log("App loaded");
    this.fetchData();
  },
  methods: {
    async fetchData() {
      let data = await d3.json("./data/tweets.json");
      this.loadData = data;
    }
  }
};
</script>

<style lang="scss">
@import "styles/views/home.scss";
</style>
