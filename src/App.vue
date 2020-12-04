<template>
  <div id="app">
    <EditorView />
  </div>
</template>

<script>
import EditorView from "./components/EditorView";

export default {
  name: "App",
  components: {
    EditorView,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  min-width: 800px;
  min-height: 600px;
}
</style>
