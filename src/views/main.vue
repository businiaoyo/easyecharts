<template>
  <div>
    <DoubleLayout>
      <template v-slot:left>
        <OptionEdit></OptionEdit>
      </template>
      <template v-slot:right>
        <EchartsCard></EchartsCard>
      </template>
    </DoubleLayout>
  </div>
</template>

<script setup lang="ts">
import DoubleLayout from "./layout/doubleLayout.vue";
import OptionEdit from "../components/optionEdit.vue";
import EchartsCard from "../components/echartsCard.vue";
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
