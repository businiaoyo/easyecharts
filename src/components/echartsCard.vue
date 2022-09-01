<script setup lang="ts">
import * as echarts from "echarts";
import { ref } from "vue";
import { onMounted, watch } from "vue";

interface Props {
  option: any;
}
const props = defineProps<Props>();
const { option } = props;

const map = ref(null);

let myChart: echarts.ECharts;
onMounted(() => {
  if (map.value) {
    myChart = echarts.init(map.value);
    myChart.setOption(option);
  }
});
watch(
  () => props.option,
  (newVal) => {
    myChart.setOption(newVal);
  },
  { deep: true }
);
</script>

<template>
  <div ref="map" style="width: 100%; height: 500px"></div>
</template>
