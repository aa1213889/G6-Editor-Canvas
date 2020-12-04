<template>
  <div class="view">
    <div id="container" />
  </div>
</template>

<script>
import G6 from "@antv/g6";

export default {
  name: "HelloWorld",
  created() {},
  data() {
    return {
      graph: null,
      nodeData: null,
    };
  },
  mounted() {
    this.getNodeData(); //step1 获取node数据
  },
  methods: {
    gSixOption() {
      this.graph = new G6.Graph({
        container: "container", //绑定id
        width: 800,
        height: 800,
        modes: {
          default: ["drag-combo"],
        },
        defaultNode: {
          shape: "circle",
          size: [50],
          color: "#5B8FF9",
          style: {
            fill: "#9EC9FF",
            lineWidth: 3,
          },
          labelCfg: {
            style: {
              fill: "#fff",
              fontSize: 20,
            },
          },
        },
        defaultEdge: {
          style: {
            stroke: "#e2e2e2",
          },
        },
      });
      this.renderG6();
      this.nodeClick();
    },
    nodeClick() {
      this.graph.on("node:click", (evt) => {
        const item = evt.item; // 被操作的节点 item
        const target = evt.target; // 被操作的具体图形
        console.log(item, target);
      });
      this.graph.on("node:dragstart", (evt) => {
        const item = evt.item; // 被操作的节点 item
        const target = evt.target; // 被操作的具体图形
        console.log(item, target);
      });
    },
    // async getNodeData() {
    //   const response = await fetch(
    //     "https://gw.alipayobjects.com/os/basement_prod/6cae02ab-4c29-44b2-b1fd-4005688febcb.json"
    //   );
    //   this.nodeData = await response.json();
    //   window.console.log(this.nodeData);
    //   this.gSixOption(); //step2 创建关系图
    // },
    getNodeData() {
      this.nodeData = {
        // 点集
        nodes: [
          {
            id: "node1", // 节点的唯一标识
            x: 100, // 节点横坐标
            y: 200, // 节点纵坐标
            label: "点1", // 节点文本
            type: "ellipse",
          },
          {
            id: "node2",
            x: 300,
            y: 200,
            label: "点2",
            visible: true, // 控制初次渲染显示与隐藏，若为 false，代表隐藏。默认不隐藏
            labelCfg: {
              // 标签配置属性
              positions: "center", // 标签的属性，标签在元素中的位置
              style: {
                // 包裹标签样式属性的字段 style 与标签其他属性在数据结构上并行
                fontSize: 12, // 标签的样式属性，文字字体大小
                // ...            // 标签的其他样式属性
              },
            },
            style: {
              // 包裹样式属性的字段 style 与其他属性在数据结构上并行
              fill: "#fff", // 样式属性，元素的填充色
              stroke: "#888", // 样式属性，元素的描边色
              // ...              // 其他样式属性
            },
          },
          {
            id: "node3",
            x: 100,
            y: 400,
            label: "点3",
          },
          {
            id: "node4",
            x: 400,
            y: 500,
            label: "点4",
          },
        ],
        // 边集
        edges: [
          // 表示一条从 node1 节点连接到 node2 节点的边
          {
            source: "node1", // 起始点 id
            target: "node2", // 目标点 id
            label: "我是连线", // 边的文本
          },
          {
            source: "node2", // 起始点 id
            target: "node3", // 目标点 id
            label: "我是连线", // 边的文本
          },
          {
            source: "node1", // 起始点 id
            target: "node3", // 目标点 id
            label: "我是连线", // 边的文本
          },
          {
            source: "node1", // 起始点 id
            target: "node4", // 目标点 id
            label: "我是连线", // 边的文本
          },
          {
            source: "node2", // 起始点 id
            target: "node4", // 目标点 id
            label: "我是连线", // 边的文本
          },
          {
            source: "node3", // 起始点 id
            target: "node4", // 目标点 id
            label: "我是连线", // 边的文本
          },
        ],
      };
      this.gSixOption(); //step2 创建关系图
    },
    renderG6() {
      this.graph.data(this.nodeData); //step3 绑定数据
      this.graph.render(); //step4 渲染
    },
  },
};
</script>

<style scoped>
.view {
  width: 100%;
  height: 100%;
}
</style>
