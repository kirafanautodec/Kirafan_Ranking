<template>
  <div id="app">
    <div id="csvinput">CSVINPUT</div>
    <div id="render">
      <RankLine v-for="rank in ranks" :rank="rank" :key="rank.name" />
    </div>
  </div>
</template>

<script>
import RankLine from "./components/RankLine.vue";

export default {
  name: "app",
  components: {
    RankLine
  },
  data() {
    return {
      ranks: [
        {
          name: "EX",
          charas: [{ id: 10002000, weapon: 4, limited: 0 }]
        },
        {
          name: "SSSS",
          charas: [{ id: 14002000, weapon: 4, limited: 0 }]
        },
        {
          name: "SSS",
          charas: [
            { id: 14002000, weapon: 4, limited: 0 },
            { id: 15012000, weapon: 4, limited: 0 }
          ]
        },
        {
          name: "SS",
          charas: [
            { id: 14002000, weapon: 4, limited: 0 },
            { id: 15012000, weapon: 4, limited: 0 },
            { id: 14032000, weapon: 4, limited: 0 },
            { id: 15042000, weapon: 4, limited: 0 },
            { id: 14022000, weapon: 4, limited: 0 }
          ]
        },
        {
          name: "S",
          charas: [
            { id: 14002000, weapon: 4, limited: 0 },
            { id: 14010000, weapon: 4, limited: 0 },
            { id: 14011000, weapon: 4, limited: 0 },
            { id: 14020000, weapon: 4, limited: 0 },
            { id: 14021000, weapon: 4, limited: 0 },
            { id: 14030000, weapon: 4, limited: 0 },
            { id: 15002000, weapon: 4, limited: 0 },
            { id: 15010000, weapon: 4, limited: 0 },
            { id: 15011000, weapon: 4, limited: 0 },
            { id: 15020000, weapon: 4, limited: 0 },
            { id: 15021000, weapon: 4, limited: 0 },
            { id: 15030000, weapon: 4, limited: 0 }
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  margin: 0px !important;
  padding: 0px !important;
}
#render {
  width: 128 * 6 + 128px;
  margin: 20px;
  display: flex;
  flex-wrap: wrap;
}
</style>
