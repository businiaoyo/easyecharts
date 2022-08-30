<template>
  <div style="display: flex">
    <div style="background-color: #f5f6fa; width: 30vw; height: 100vh">
      <slot name="left"></slot>
    </div>
    <div style="flex: 1; background-color: #ecf0f1; height: 100vh">
      <slot name="right"></slot>
    </div>
  </div>
</template>
<script lang="ts" setup></script>
