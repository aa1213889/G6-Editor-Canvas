<template>
  <div id="app">
    <Demo2 />
  </div>
</template>

<script>
import Demo2 from "./components/Demo2";

export default {
  name: "App",
  components: {
    Demo2,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
}
</style>
