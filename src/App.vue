<template>
  <div id="app">
    <!-- <img alt="ARENA Workshop" src="./assets/loading.gif"> -->
    <RandomWord />
  </div>
</template>

<script>
import RandomWord from "./components/RandomWord.vue";

export default {
  name: "app",
  components: {
    RandomWord
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
