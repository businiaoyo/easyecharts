<template>
  <div>
    <Codemirror :doc="option" :submit="updateOption"></Codemirror>
  </div>
</template>
<script setup lang="ts">
import { registerRuntimeCompiler } from "vue";
import Codemirror from "./edit/codemirror.vue";
interface Props {
  option: any;
  reRun(option: Object): void;
}
const { option, reRun } = defineProps<Props>();
const updateOption = (option: Object) => {
  console.log("runOption", option);
  reRun(option);
};
</script>
