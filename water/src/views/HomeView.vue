<template>
  <div class="content-body">
    <div class="header">
      <div class="header-left">
        <span>水质情况实时监测预警系统</span>
      </div>
      <div class="header-time">
        <span id="time">{{ nowDate }} {{ nowTime }} {{ nowWeek }}</span>
      </div>
    </div>

    <div class="content">
      <div class="content-con">
        <!-- 大屏左边部件 -->
        <div class="left-body">
          <LeftTop></LeftTop>
          <LeftCon></LeftCon>
          <LeftBottom></LeftBottom>
        </div>
        <!-- 大屏中边部件 -->
        <CenterBody></CenterBody>
        <!-- 大屏右边边部件 -->
        <div class="right-body">
          <RightTop></RightTop>
          <RightCon></RightCon>
          <RightBottom></RightBottom>
        </div>
      </div>
    </div>
  </div>

  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div> -->
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import LeftTop from "@/components/water-left/left-top.vue";
import LeftCon from "@/components/water-left/left-con.vue";
import LeftBottom from "@/components/water-left/left-bottom.vue";
import RightTop from "@/components/water-right/right-top.vue";
import RightCon from "@/components/water-right/right-con.vue";
import RightBottom from "@/components/water-right/right-bottom.vue";
import CenterBody from "@/components/water-conter/conter.vue";

export default {
  name: "HomeView",
  components: {
    LeftTop,
    LeftCon,
    LeftBottom,
    RightTop,
    RightCon,
    RightBottom,
    CenterBody,
  },
  data() {
    return {
      nowDate: "",
      nowTime: "",
      nowWeek: "",
    };
  },
  mounted() {
    // 页面加载完后显示当前时间
    this.dealWithTime(new Date());
    // 定时刷新时间
    this.timer = setInterval(() => {
      this.dealWithTime(new Date()); // 修改数据date
    }, 500);
  },
  destroyed() {
    if (this.timer) {
      // 注意在vue实例销毁前，清除我们的定时器
      clearInterval(this.timer);
    }
  },
  methods: {
    dealWithTime(data) {
      // 获取当前时间
      let formatDateTime;
      let Y = data.getFullYear();
      let M = data.getMonth() + 1;
      let D = data.getDate();
      let H = data.getHours();
      let Min = data.getMinutes();
      let S = data.getSeconds();
      let W = data.getDay();
      H = H < 10 ? "0" + H : H;
      Min = Min < 10 ? "0" + Min : Min;
      S = S < 10 ? "0" + S : S;
      switch (W) {
        case 0:
          W = "日";
          break;
        case 1:
          W = "一";
          break;
        case 2:
          W = "二";
          break;
        case 3:
          W = "三";
          break;
        case 4:
          W = "四";
          break;
        case 5:
          W = "五";
          break;
        case 6:
          W = "六";
          break;
        default:
          break;
      }
      this.nowDate = Y + "年" + M + "月" + D + "日 ";
      this.nowWeek = "星期" + W;
      this.nowTime = H + ":" + Min + ":" + S;
      // formatDateTime = Y + "年" + M + "月" + D + "日 " + " 周" +W + H + ":" + Min + ":" + S;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
body {
  width: 100%;
  height: 100%;
  overflow: auto;
}

.content-body {
  width: 100%;
  height: 100%;
  background: #0d325f;
  background-size: 100% 100%;
  position: absolute;
}

.header {
  height: 70px;
  width: 100%;
  /*    border: 1px solid red;*/
}
.header .header-left {
  width: 50%;
  float: left;
  line-height: 70px;
}
.header .header-left span {
  color: #ffffff;
  font-weight: bold;
  font-size: 24px;
  letter-spacing: 2px;
  padding: 0 20px;
}
.header .header-time {
  width: 48%;
  line-height: 70px;
  float: right;
  text-align: right;
  padding-right: 20px;
}
.header .header-time span {
  color: #ffffff;
}

.content {
  width: 100%;
  height: calc(100% - 75px);
  position: absolute;
}
.content .content-con {
  height: 100%;
}
.content .content-con .left-body {
  width: 22%;
  height: 100%;
  float: left;
  margin: 0 0.3%;
}

.right-body {
  width: 22%;
  height: 100%;
  float: right;
  margin: 0 0.3%;
}
</style>
