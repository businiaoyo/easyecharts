<template>
  <div>
    <Easyecharts :option="option" title="demoView"></Easyecharts>
  </div>
</template>

<script>
const option = {
  xAxis: {
    type: "category",
    data: ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"],
  },
  yAxis: {
    type: "value",
  },
  series: [
    {
      data: [120, 200, 150, 80, 70, 110, 130],
      type: "bar",
      showBackground: true,
      backgroundStyle: {
        color: "rgba(180, 180, 180, 0.2)",
      },
    },
  ],
};
import Easyecharts from "../components/easyecharts.vue";
export default {
  components: { Easyecharts },
  data() {
    return {
      option: option,
    };
  },
};
</script>

<style></style>
