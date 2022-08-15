<template>
  <div>
    {{ option }}
  </div>
</template>
<script setup lang="ts">
import { reactive } from "vue";
const option = reactive({ option: "opt" });
</script>
