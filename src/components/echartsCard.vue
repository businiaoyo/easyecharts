<script setup lang="ts">
import * as echarts from "echarts";
import { ref } from "vue";
import { onMounted } from "vue";

interface Props {
  option: any;
}
const { option } = defineProps<Props>();
const map = ref(null);

onMounted(() => {
  if (map.value) {
    let myChart = echarts.init(map.value);
    console.log(myChart);
    myChart.setOption(option);
  }
});
</script>

<template>
  <div ref="map" style="width: 100%; height: 500px"></div>
</template>
