<template>
  <div class="toolBar">
    <el-button>发布</el-button>
  </div>
  <div ref="textarea" class="w-full h-500"></div>
</template>

<script lang="ts" setup>
import { EditorState } from "@codemirror/state";
import { EditorView, keymap } from "@codemirror/view";
import { defaultKeymap } from "@codemirror/commands";

import { ref, onMounted, watchEffect } from "vue";
import { time } from "echarts";

const props = defineProps({
  doc: Object,
});
const { doc } = props;

let textarea = ref();

let startState = EditorState.create({
  doc: JSON.stringify(doc, null, "\t"),
  extensions: [keymap.of(defaultKeymap)],
});

onMounted(() => {
  let view = new EditorView({
    state: startState,
    parent: textarea.value,
  });

  // 监听输入，同步获取编辑器中的数据
  const stop = watchEffect(() => {
    setTimeout(() => {
      console.log("options update:", JSON.parse(String(view.state.doc)));
    }, 3000);
  });
});
</script>

<style>
.toolBar {
  background-color: aquamarine;
  display: flex;
  justify-content: flex-end;
}
</style>
