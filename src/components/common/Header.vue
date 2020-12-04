<template>
  <div class="header">
    {{ title }}
  </div>
</template>

<script>
export default {
  name: "Header",
  props: {
    title: String,
  },
};
</script>

<style>
.header {
  width: 100%;
  height: 30px;
}
</style>
