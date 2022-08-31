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

onMounted(() => {
  if (map.value) {
    let myChart = echarts.init(map.value);
    console.log(myChart);
    myChart.setOption(option);
  }
});
watch(
  () => props.option as Object,
  (newVal, oldVal) => {
    console.log("option updated");
  }
);
</script>

<template>
  <div ref="map" style="width: 100%; height: 500px"></div>
</template>
