<template>
  <div style="width: inherit">
    <DoubleLayout>
      <template v-slot:left>
        <OptionEdit :option="options" :re-run="reRun"></OptionEdit>
      </template>
      <template v-slot:right>
        <div style="margin-top: 20vh; margin-left: 20px">
          <EchartsCard :option="options"></EchartsCard>
        </div>
      </template>
    </DoubleLayout>
  </div>
</template>

<script setup lang="ts">
import DoubleLayout from "./layout/doubleLayout.vue";
import OptionEdit from "../components/optionEdit.vue";
import EchartsCard from "../components/echartsCard.vue";
import { reactive } from "vue";
let options: Object = reactive({
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
});
const reRun: (option: Object) => void = (option) => {
  options = option;
};
</script>
