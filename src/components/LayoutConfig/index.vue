<template>
  <div class="layout-config">
    <Header title="画布配置" />
  </div>
</template>

<script>
import Header from "../common/Header";
export default {
  name: "LayoutConfig",
  components: {
    Header,
  },
};
</script>

<style>
.layout-config {
  width: 200px;
  height: 100%;
}
</style>
