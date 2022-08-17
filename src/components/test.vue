<!-- <template>
  <input ref="input" />
</template>
<script setup lang="ts">
import { ref, onMounted } from "vue";
onMounted(() => {
  const input = ref(null);
  console.log("input", input.value);
});
</script> -->

<script setup lang="ts">
import { ref, onMounted } from "vue";

// 声明一个 ref 来存放该元素的引用
// 必须和模板里的 ref 同名

onMounted(() => {
  const input: any = ref(null);
  input.value.focus();
});
</script>

<template>
  <input ref="input" />
</template>
