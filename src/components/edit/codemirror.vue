<template>
  <div class="toolBar">
    <el-button
      class="bg-sky-500 w-[50px] leading-[30px] text-center cursor-pointer"
      @click="doSubmit"
      >运行</el-button
    >
  </div>
  <div ref="textarea" class="w-full h-500"></div>
</template>

<script lang="ts" setup>
import { EditorState } from "@codemirror/state";
import { EditorView, keymap } from "@codemirror/view";
import { defaultKeymap } from "@codemirror/commands";
import { ref, onMounted, watchEffect, reactive } from "vue";

const props = defineProps({
  doc: Object,
  submit: Function,
});
const { doc, submit } = props;

let textarea = ref();
let startState = EditorState.create({
  doc: JSON.stringify(doc, null, "\t"),
  extensions: [keymap.of(defaultKeymap)],
});

let view: any = reactive({});
onMounted(() => {
  view = new EditorView({
    state: startState,
    parent: textarea.value,
  });
});

const doSubmit = () => {
  if (submit) {
    submit(JSON.parse(String(view.state.doc)));
  }
  // 监听输入，同步获取编辑器中的数据
  // const stop = watchEffect(() => {
  // setTimeout(() => {
  // console.log("options update:", JSON.parse(String(view.state.doc)));
  // }, 3000);
  // });
};
onMounted(() => {});
</script>

<style>
.toolBar {
  background-color: aquamarine;
  display: flex;
  justify-content: flex-end;
  height: 30px;
}
</style>
