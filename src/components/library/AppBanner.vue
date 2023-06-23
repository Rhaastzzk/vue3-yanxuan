<template>
  <el-carousel height="500px" :interval="2000" :autoplay="true">
    <el-carousel-item v-for="(item, index) in list" :key="index">
      <img :src="item" alt="" class="carousel-image">
    </el-carousel-item>
  </el-carousel>
</template>

<script>
export default {
  name: "AppBanner",
  data() {
    return {
      list: ["https://m.360buyimg.com/babel/jfs/t1/136631/31/37730/248268/64745e08F3ece9db6/c9a72df17be9d19a.png",
        require("../../assets/images/banner.png"),
        "https://m.360buyimg.com/babel/jfs/t1/102657/4/38889/138406/647551f4Fc62c3756/6ec4089d21587dd0.jpg.webp",
        require("../../assets/images/banner.webp"),
        require("../../assets/images/laolao.jpg")
      ]
    };
  }
};
</script>

<style lang="less" scoped>
.carousel-image {
  width: 100%;
  /* 设置图片宽度为100% */
  height: 100%;
  /* 设置图片高度自适应 */
}
</style>
