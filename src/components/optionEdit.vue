<template>
  <div>
    {{ option }}
  </div>
</template>
<script setup lang="ts">
interface Props {
  option: any;
}
const { option } = defineProps<Props>();
</script>
