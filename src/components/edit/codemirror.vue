<template>
  <hr />
  <div ref="textarea" style="width: 100%; height: 500px"></div>
</template>

<script lang="ts" setup>
import { EditorState } from "@codemirror/state";
import { EditorView, keymap } from "@codemirror/view";
import { defaultKeymap } from "@codemirror/commands";

import { ref, onMounted } from "vue";

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
  console.log("textarea", textarea);
});
</script>

<style></style>
