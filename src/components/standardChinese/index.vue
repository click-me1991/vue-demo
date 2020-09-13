<template>
  <Module>
    <ModuleTitleLayout>
      <ModuleTitle title="普通话等级"></ModuleTitle>
    </ModuleTitleLayout>
    <div class="chart" id="standard-chinese-chart"></div>
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
        grid: {
          top: 0,
          bottom: 0
        },
        color: [
          "#0459FF",
          "#FF9933",
          "#00FCFF",
          "#00C646",
          "#9054FF",
          "#FF7ED6"
        ],
        legend: {
          orient: "vertical",
          left: 10,
          top: 5,
          itemWidth: 10,
          itemHeight: 10,
          borderRadius: 10,
          textStyle: {
            color: "#fff",
            fontSize: "12"
          },
          data: [
            "一级甲等：10%",
            "一级乙等： 30%",
            "二级甲等： 40%",
            "二级乙等： 5%",
            "三级甲等： 5%",
            "三级乙等： 10%"
          ]
        },
        series: [
          {
            name: "访问来源",
            type: "pie",
            radius: ["0%", "80%"],
            center: ["65%", "50%"],
            label: {
              show: false
            },
            data: [
              { value: 335, name: "一级甲等：10%" },
              { value: 310, name: "一级乙等： 30%" },
              { value: 234, name: "二级甲等： 40%" },
              { value: 135, name: "二级乙等： 5%" },
              { value: 234, name: "三级甲等： 5%" },
              { value: 135, name: "三级乙等： 10%" }
            ]
          }
        ]
      }
    };
  },
  mounted() {
    this.myChart = echarts.init(
      document.getElementById("standard-chinese-chart")
    );
    this.myChart.setOption(this.chartOption);
  }
};
</script>

<style lang="less" scoped>
.chart {
  width: 100%;
  height: 140px;
  margin-top: 0.2rem;
}
</style>
