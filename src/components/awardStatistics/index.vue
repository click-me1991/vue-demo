<template>
  <Module>
    <ModuleTitleLayout>
      <ModuleTitle title="教师获奖统计"></ModuleTitle>
    </ModuleTitleLayout>
    <div class="chart" id="award-statistics-chart"></div>
  </Module>
</template>

<script>
import echarts from "echarts";
import Module from "../common/Module";
import ModuleTitleLayout from "../common/ModuleTitleLayout";
import ModuleTitle from "../common/ModuleTitle";
export default {
  name: "SubjectDistribution",
  components: {
    ModuleTitle,
    Module,
    ModuleTitleLayout
  },
  data() {
    return {
      myChart: null,
      chartOption: {
        color: ["#FF9933"],
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
          }
        },
        yAxis: {
          axisTick: {
            show: false
          },
          axisLine: {
            lineStyle: {
              color: "#135BAD"
            }
          },
          type: "category",
          data: ["衬衫", "羊毛衫", "雪纺衫", "裤子"]
        },
        series: [
          {
            name: "销量",
            type: "bar",
            label: {
              show: true,
              position: "right",
              formatter: "{c}人"
            },
            data: [5, 20, 36, 10]
          }
        ]
      }
    };
  },
  mounted() {
    this.myChart = echarts.init(
      document.getElementById("award-statistics-chart")
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
