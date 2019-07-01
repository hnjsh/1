<template>
    <div class="page">
      <el-carousel indicator-position="outside" height="560px" arrow="always">
        <el-carousel-item v-for="item in 6" :key="item">
          <h3>{{ item }}</h3>
        </el-carousel-item>
      </el-carousel>
      <el-backtop target=".page-component__scroll .el-scrollbar__wrap"></el-backtop>
    </div>
</template>

<script>
    export default {
        name: "homePage"
    }
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  .el-carousel__item h3 {
    color: #475669;
    font-size: 18px;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
  }
  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }
  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }.el-carousel__item h3 {
     color: #475669;
     font-size: 18px;
     opacity: 0.75;
     line-height: 300px;
     margin: 0;
   }
  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }
  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
  /*指示器大小*/
  .el-carousel__arrow{
    height: 70px !important;
    width: 70px !important;
  }

  .el-carousel__indicators--outside{
    display: none;
  }

</style>
