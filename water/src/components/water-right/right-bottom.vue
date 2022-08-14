<template>
  <div class="right-bottom public-bg">
    <div class="public-title">主要地区水流量</div>
    <div class="title-nav" ref="zhexian"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "RightBottom",
  components: {},
  props: {},
  data() {
    return {};
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {
    this.zhexian();
  },
  methods: {
    zhexian() {
      var myChart = echarts.init(this.$refs.zhexian);

      var dataText = [
        {
          name: "上游流速",
          type: "line",
          smooth: true,
          symbolSize: 8,
          data: [127, 224, 120, 278, 227, 237],
          barWidth: "30%",
          itemStyle: {
            normal: {
              color: "#f0c725",
            },
          },
        },
        {
          name: "下游流速",
          type: "line",
          smooth: true,
          symbolSize: 8,
          data: [27, 124, 70, 178, 127, 157],
          barWidth: "30%",
          itemStyle: {
            normal: {
              color: "#16f892",
            },
          },
        },
        {
          name: "平均流速",
          type: "line",
          smooth: true,
          symbolSize: 8,
          data: [127, 74, 120, 99, 130, 355],
          barWidth: "30%",
          itemStyle: {
            normal: {
              color: "#0BE3FF",
            },
          },
        },
      ];
      var dataObj = {
        year: ["2015", "2016", "2017", "2018", "2019", "2020"],
        data: {
          value: [
            {
              name: "上游流速",
              value: [127, 224, 250, 278, 227, 355],
            },
            {
              name: "下游流速",
              value: [27, 124, 70, 178, 127, 157],
            },
            {
              name: "平均流速",
              value: [127, 74, 120, 99, 130, 50],
            },
          ],
        },
      };
      let dataArr = [];

      dataObj.data.value.map((item) => {
        let datachild = [];
        let newArr = {
          name: item.name,
          type: "line",
          smooth: true,
          symbolSize: 8,
          data: item.value,
          barWidth: "30%",
          itemStyle: {
            normal: {
              color:
                item.name === "上游流速"
                  ? "#f0c725"
                  : item.name === "下游流速"
                  ? "#0BE3FF"
                  : "#16f892",
            },
          },
        };

        dataArr.push(newArr);
      });
      var option = {
        color: ["#f0c725", "#16f892"],
        title: {
          left: "center",
          text: "",
          textStyle: {
            color: "#FFFFFF",
            fontSize: "14",
          },
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            // 坐标轴指示器，坐标轴触发有效
            type: "shadow", // 默认为直线，可选为：'line' | 'shadow'
          },
        },
        legend: {
          x: "center",
          top: "25",
          textStyle: {
            color: "#c1cadf",
            fontSize: 14,
          },
        },
        grid: {
          left: "6%",
          right: "4%",
          top: "25%",
          bottom: "3%",
          containLabel: true,
        },
        toolbox: {
          show: true,
          orient: "vertical",
          x: "right",
          y: "center",
        },
        xAxis: [
          {
            type: "category",
            boundaryGap: false,
            data: dataObj.year,
            axisLine: {
              lineStyle: {
                color: "rgba(240,199,37,0.5)",
              },
            },
            axisLabel: {
              interval: 0,
              color: "#c1cadf",
              fontSize: "15",
            },
          },
        ],
        yAxis: [
          {
            type: "value",
            name: "(m3)",
            nameTextStyle: {
              color: "#c1cadf",
              align: "right",
              lineHeight: 10,
            },
            axisLine: {
              lineStyle: {
                color: "rgba(240,199,37,0.5)",
              },
            },
            axisLabel: {
              interval: 0,
              color: "#c1cadf",
              fontSize: "15",
            },
            splitLine: {
              show: false,
            },
          },
        ],
        series: dataArr,
      };
      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
      // window.addEventListener("resize", function () {
      //   myChart.resize();
      // });
    },
  },
};
</script>

<style>
.right-body .right-bottom {
  width: 100%;
  height: 39%;
  margin-top: 2%;
}
</style>
