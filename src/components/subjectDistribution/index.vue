<template>
  <Module>
    <ModuleTitleLayout>
      <ModuleTitle></ModuleTitle>
      <SwitchBtn slot="right"></SwitchBtn>
    </ModuleTitleLayout>
    <div class="chart" id="subject-distribution-chart"></div>
  </Module>
</template>

<script>
import echarts from "echarts";
import Module from "../common/Module";
import ModuleTitleLayout from "../common/ModuleTitleLayout";
import ModuleTitle from "../common/ModuleTitle";
import SwitchBtn from "../common/SwitchBtn";
export default {
  name: "SubjectDistribution",
  components: {
    ModuleTitle,
    Module,
    ModuleTitleLayout,
    SwitchBtn
  },
  data() {
    return {
      myChart: null,
      chartOption: {
        color: ["#258DF4"],
        textStyle: {
          color: "#fff"
        },
        grid: {
          left: 30,
          right: 0,
          top: 10,
          bottom: 20
        },
        xAxis: {
          axisTick: {
            show: false
          },
          axisLine: {
            lineStyle: {
              color: "#135BAD"
            }
          },
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子", "高跟鞋", "袜子"]
        },
        yAxis: {
          axisTick: {
            show: false
          },
          axisLine: {
            lineStyle: {
              color: "#135BAD"
            }
          }
        },
        series: [
          {
            name: "销量",
            type: "bar",
            label: {
              show: true,
              position: "top",
              formatter: "{c}人"
            },
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      }
    };
  },
  mounted() {
    this.myChart = echarts.init(
      document.getElementById("subject-distribution-chart")
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
