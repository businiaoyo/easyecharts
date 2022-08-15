<template>
  <div style="display: flex">
    <div style="background-color: red; width: 400px">
      <slot name="left"></slot>
    </div>
    <div style="flex: 1; background-color: pink">
      <slot name="right"></slot>
    </div>
  </div>
</template>
<script lang="ts" setup></script>
