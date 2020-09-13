<template>
  <Module>
    <ModuleTitleLayout>
      <ModuleTitle title="学校分布"></ModuleTitle>
      <ChartLabel slot="right"></ChartLabel>
    </ModuleTitleLayout>
    <div class="chart" id="school-distribution-chart"></div>
  </Module>
</template>

<script>
import echarts from "echarts";
import Module from "../common/Module";
import ModuleTitleLayout from "../common/ModuleTitleLayout";
import ModuleTitle from "../common/ModuleTitle";
import ChartLabel from "./ChartLabel";
export default {
  name: "SubjectDistribution",
  components: {
    ModuleTitle,
    Module,
    ModuleTitleLayout,
    ChartLabel
  },
  data() {
    return {
      myChart: null,
      chartOption: {
        color: ["#00FCFF", "#00C646", "#125BE1"],
        textStyle: {
          color: "#fff"
        },
        grid: {
          left: 0,
          right: 0,
          top: 20,
          bottom: 40
        },
        dataset: {
          source: [
            ["product", "2015", "2016", "2017"],
            ["幼儿园\n36所", 43.3, 85.8, 93.7],
            ["小学\n20所", 83.1, 73.4, 55.1],
            ["初中\n40所", 86.4, 65.2, 82.5],
            ["高中\n10所", 72.4, 53.9, 39.1]
          ]
        },
        xAxis: {
          type: "category",
          axisLine: {
            lineStyle: {
              color: "#135BAD"
            }
          },
          axisTick: {
            show: false
          },
          axisLabel: {
            lineHeight: 15
          }
        },
        yAxis: {
          show: false
        },
        series: [{ type: "bar" }, { type: "bar" }, { type: "bar" }]
      }
    };
  },
  mounted() {
    this.myChart = echarts.init(
      document.getElementById("school-distribution-chart")
    );
    this.myChart.setOption(this.chartOption);
  }
};
</script>

<style lang="less" scoped>
.chart {
  width: 100%;
  height: 120px;
  margin-top: 0.2rem;
}
</style>
