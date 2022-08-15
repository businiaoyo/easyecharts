<template>
  <div ref="map" style="width: 100%; height: 500px"></div>
</template>

<script setup lang="ts">
// import * as echarts from "echarts";
import { ref } from "vue";
import { onMounted } from "vue";

let option = {
  title: {
    text: "ECharts 入门示例",
  },
  tooltip: {},
  legend: {
    data: ["销量"],
  },
  xAxis: {
    data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"],
  },
  yAxis: {},
  series: [
    {
      name: "销量",
      type: "bar",
      data: [5, 20, 36, 10, 10, 20],
    },
  ],
};
onMounted(() => {
  const map = ref();
  console.log("map.value", map.value);
});
// if (map) {
//   let myChart = echarts.init(map);
//   console.log(myChart);
//   myChart.setOption(option);
// }
</script>
