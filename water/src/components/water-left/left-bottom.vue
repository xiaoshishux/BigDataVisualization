<template>
  <div class="left-bottom public-bg">
    <div class="public-title">企业污染排放情况</div>
    <div class="title-nav" ref="wuran"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "LeftBottom",
  components: {},
  props: {},
  data() {
    return {};
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {
    this.wuran();
  },
  methods: {
    wuran() {
      var myChart = echarts.init(this.$refs.wuran);
      var salvProName = [
        "企业总数",
        "废气企业",
        "废水企业",
        "铅污染",
        "铬污染",
      ];
      var salvProValue = [117, 74, 72, 67, 55];
      var salvProMax = []; //背景按最大值
      for (let i = 0; i < salvProValue.length; i++) {
        salvProMax.push(salvProValue[0]);
      }
      let option = {
        grid: {
          left: "2%",
          right: "2%",
          bottom: "-6%",
          top: "8%",
          containLabel: true,
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "none",
          },
          formatter: function (params) {
            return params[0].name + " : " + params[0].value;
          },
        },
        xAxis: {
          show: false,
          type: "value",
        },
        yAxis: [
          {
            type: "category",
            inverse: true,
            axisLabel: {
              show: true,
              textStyle: {
                color: "#fff",
              },
            },
            splitLine: {
              show: false,
            },
            axisTick: {
              show: false,
            },
            axisLine: {
              show: false,
            },
            data: salvProName,
          },
          {
            type: "category",
            inverse: true,
            axisTick: "none",
            axisLine: "none",
            show: true,
            axisLabel: {
              textStyle: {
                color: "#ffffff",
                fontSize: "12",
              },
            },
            data: salvProValue,
          },
        ],
        series: [
          {
            name: "值",
            type: "bar",
            zlevel: 1,
            itemStyle: {
              normal: {
                barBorderRadius: 30,
                color: new echarts.graphic.LinearGradient(0, 0, 1, 0, [
                  {
                    offset: 0,
                    color: "rgb(57,89,255,1)",
                  },
                  {
                    offset: 1,
                    color: "rgb(46,200,207,1)",
                  },
                ]),
              },
            },
            barWidth: 10,
            data: salvProValue,
          },
          {
            name: "背景",
            type: "bar",
            barWidth: 10,
            barGap: "-100%",
            data: salvProMax,
            itemStyle: {
              normal: {
                color: "rgba(24,31,68,1)",
                barBorderRadius: 30,
              },
            },
          },
        ],
      };

      myChart.setOption(option);
    },
  },
};
</script>

<style>
.left-bottom {
  width: 100%;
  height: 32%;
  margin-top: 1.6%;
}
.title-nav {
  width: 100%;
  height: calc(100% - 30px);
}
</style>
