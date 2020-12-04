<template>
  <div class="editor-view">
    <ToolBar />
    <div class="editor-view-container">
      <ElementBox />
      <Canvas />
      <div class="editor-container-right">
        <div class="container-right-content">
          <LayoutConfig v-show="crVisiable" />
          <ContextMenu v-show="!crVisiable" />
        </div>
        <MiniMap />
      </div>
    </div>
  </div>
</template>

<script>
import ToolBar from "./ToolBar";
import ElementBox from "./ElementBox";
import Canvas from "./Canvas";
import MiniMap from "./MiniMap";
import ContextMenu from "./ContextMenu";
import LayoutConfig from "./LayoutConfig";
export default {
  name: "EditorView",
  components: {
    ToolBar,
    ElementBox,
    Canvas,
    MiniMap,
    ContextMenu,
    LayoutConfig,
  },
  data() {
    return {
      crVisiable: true, //控制LayoutConfig ContextMenu显示
    };
  },
};
</script>

<style>
.editor-view {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.editor-view-container {
  flex: 1;
  background-color: gray;
  display: flex;
}
.editor-view-container .editor-container-right {
  width: 200px;
  height: 100%;
  background-color: greenyellow;
  display: flex;
  flex-direction: column;
}
.editor-view-container .editor-container-right .container-right-content {
  flex: 1;
  background-color: gold;
}
</style>
