<template>
  <div class="left-top public-bg">
    <div class="public-title">重点水质量检测区</div>
    <div class="top-body">
      <div class="top-left">
        <div class="top-left-title">
          <h6>注水量</h6>
          <span><b>1756</b>m3/h</span>
          <img
            src="../../assets/pictre.png"
          />
        </div>
      </div>
      <div class="top-right">
        <div class="top-left-title">
          <h6>泄水量</h6>
          <span><b>3520</b>m3/h</span>
          <img
            src="../../assets/pictre.png"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LeftTop",
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
.public-bg{
    background: rgba(12,26,63,0.3);
}

.public-title{
    width: calc(100% - 20px);
    height: 30px;
    position: relative;
    top: 0;
    left: 5px;
    color: white;
    padding-left: 16px;
    line-height: 30px;
    font-size: 13px;
}
.public-title:before{
    width: 4px;
    height: 20px;
    top: 5px;
    position: absolute;
    content: "";
    background: #2997e4;
    border-radius: 2px;
    left: 5px;
}
.left-top{
    width: 100%;
    height: 27%;
}
.left-top .top-body{
    width: 100%;
    height: calc(100% - 30px);
}
.left-top .top-body .top-left{
    float: left;
    width: 50%;
    height: 100%;
}
 .top-left-title{
    width: 100%;
    height: 100%;
    padding: 30px;
    box-sizing: border-box;
}
 .top-left-title h6{
    color: #bad0e2;
}
.top-left-title span{
    margin-top: 30px;
    display: inline-block;
    color: #2aa4f1;

/*    height: 80px;
    line-height: 80px;*/
}
 .top-left-title span b{
    font-size: 30px;
     letter-spacing:5px;
}
.top-left-title img{
    width: 80%;
}
.left-top .top-body .top-right{
    float: left;
    width: 50%;
    height: 100%;
}
</style>
