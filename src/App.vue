<template>
  <div id="app">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <PackChart :tweetData="loadData" />
  </div>
</template>

<script>
import * as d3 from "d3";

// import HelloWorld from './components/HelloWorld.vue';
import PackChart from "./components/Chart.vue";

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
      let data = await d3.json("tweets.json");
      this.loadData = data;
    }
  }
};
</script>

<style lang="scss">
@import "./styles/views/home.scss";
</style>
