<template>
  <div class="right-top public-bg">
    <div class="public-title">水质污染TOP5</div>
    <div class="title-nav">
      <div class="top5-ul">
        <ul>
          <li>
            <span>1</span>
            <span>严重</span>
            <span>北京市</span>
            <span>房山区</span>
            <span>重度污染</span>
            <span>15公里</span>
          </li>
          <li>
            <span>2</span>
            <span>严重</span>
            <span>上海市</span>
            <span>闵行区</span>
            <span>重度污染</span>
            <span>10公里</span>
          </li>
          <li>
            <span>3</span>
            <span>严重</span>
            <span>北京市</span>
            <span>朝阳区</span>
            <span>重度污染</span>
            <span>9.3公里</span>
          </li>
          <li>
            <span>4</span>
            <span>中度</span>
            <span>广东省</span>
            <span>广州市</span>
            <span>中度污染</span>
            <span>8.6公里</span>
          </li>
          <li>
            <span>5</span>
            <span>中度</span>
            <span>浙江省</span>
            <span>杭州市</span>
            <span>中度污染</span>
            <span>6.6公里</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RightTop",
  components: {},
  props: {},
  data() {
    return {};
  },
  computed: {},
  watch: {},
  created() {},
  mounted() {},
  methods: {},
};
</script>

<style>
.title-nav {
  width: 100%;
  height: calc(100% - 30px);
}

.right-body .right-top {
  width: 100%;
  height: 32%;
}
.title-nav .top5-ul {
  width: calc(100% - 20px);
  height: calc(100% - 30px);
  padding: 10px;
}
.title-nav .top5-ul ul {
  width: 100%;
  height: 100%;
}
.title-nav .top5-ul ul,
li {
  list-style: none;
}
.title-nav .top5-ul ul > li {
  width: 100%;
  height: 20%;
  color: #ffffff;
  line-height: 68px;
  justify-content: center;
}
.title-nav .top5-ul ul li span {
  margin-left: 3%;
  font-size: 14px;
}
.title-nav .top5-ul ul li span:nth-child(1) {
  color: #eb6841;
  font-style: oblique;
  /*width: 10%;*/
  /*#20a8fe
            #EB6841
            #3FB8AF
            #FE4365
            #FC9D9A*/
  display: inline-block;
  text-align: center;
  font-size: 20px;
}

.title-nav .top5-ul ul li span:nth-child(2) {
  width: 10%;
  display: inline-block;
  text-align: center;

  height: 30px;
  line-height: 30px;
  /*    height: 100%;*/
  /*line-height: 100%;*/
  vertical-align: center;
  border-radius: 5px;
  color: #ffffff;
}
.title-nav .top5-ul ul li:nth-child(1) span:nth-child(2),
.title-nav .top5-ul ul li:nth-child(2) span:nth-child(2),
.title-nav .top5-ul ul li:nth-child(3) span:nth-child(2) {
  background: #d89346;
}
.title-nav .top5-ul ul li:nth-child(4) span:nth-child(2),
.title-nav .top5-ul ul li:nth-child(5) span:nth-child(2) {
  background: #1db5ea;
}
.title-nav .top5-ul ul li span:nth-child(3) {
  /*width: 15%;*/
  display: inline-block;
  text-align: center;
}
.title-nav .top5-ul ul li span:nth-child(4) {
  /*width: 15%;*/
  display: inline-block;
  text-align: center;
}
.title-nav .top5-ul ul li span:nth-child(5) {
  /*width: 20%;*/
  display: inline-block;
  text-align: center;
}
.title-nav .top5-ul ul li span:nth-child(6) {
  display: inline-block;
  text-align: center;
}
</style>
