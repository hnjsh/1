<template>
    <div class="header">
      <div class="logo">
        <img src="../assets/logo.png" width="100%" height="100%">
      </div>
      <el-menu :default-active="activeIndex" class="el-menu-demo" active-text-color="#e74c3c"
               text-color="#000" mode="horizontal" @select="handleSelect">
        <el-menu-item index="1">首页</el-menu-item>
        <el-submenu index="2">
          <template slot="title">装修服务</template>
          <el-menu-item index="2-1">个性化定制</el-menu-item>
          <el-menu-item index="2-2">别墅大宅</el-menu-item>
          <el-menu-item index="2-3">全屋软装</el-menu-item>
          <el-submenu index="2-4">
            <template slot="title">装修案例</template>
            <el-menu-item index="2-4-1">热装楼盘</el-menu-item>
            <el-menu-item index="2-4-2">软装范本</el-menu-item>
            <el-menu-item index="2-4-3">门店园林</el-menu-item>
          </el-submenu>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title" class="navUnderline">服务团队</template>
          <el-menu-item index="3-1">团队定制服务</el-menu-item>
          <el-menu-item index="3-2">设计大师</el-menu-item>
          <el-menu-item index="3-3">金牌工队</el-menu-item>
        </el-submenu>
        <el-submenu index="4">
          <template slot="title">品质护航</template>
          <el-menu-item index="4-1">品牌保障</el-menu-item>
          <el-menu-item index="4-2">前沿设计</el-menu-item>
          <el-menu-item index="4-3">严选饰材</el-menu-item>
        </el-submenu>
        <el-submenu index="5">
          <template slot="title">关于我们</template>
          <el-menu-item index="5-1">加入我们</el-menu-item>
          <el-menu-item index="5-2">联系我们</el-menu-item>
          <el-menu-item index="5-3">常见问题</el-menu-item>
        </el-submenu>
        <el-button size="mini" class="quote" type="danger" round icon="el-icon-edit-outline">快速报价</el-button>
      </el-menu>

    </div>
</template>

<script>
    export default {
      name: "Header",
      data(){
        return{
          activeIndex: '1',
          activeIndex2: '1'
        }
      },
      methods:{
        handleSelect(key, keyPath) {
          console.log(key, keyPath);
        }
    }
    }
</script>

<style scoped>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  .header{
    display: flex;
    justify-content: space-around;
  }
  .logo{
    height:66px;
    width:80px;
  }
  .el-menu-demo{
    border-bottom: none;
  }
  /*导航栏hover颜色*/
  .el-menu-item:hover{
    outline: 0 !important;
    color: #409EFF !important;
  }
  .quote{
    margin: 14px 0;
  }
</style>
