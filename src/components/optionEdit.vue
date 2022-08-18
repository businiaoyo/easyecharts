<template>
  <div>
    {{ option }}
    <Codemirror :doc="option"></Codemirror>
  </div>
</template>
<script setup lang="ts">
import Codemirror from "./edit/codemirror.vue";
interface Props {
  option: any;
}
const { option } = defineProps<Props>();
</script>
