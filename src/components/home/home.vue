<template>
  <el-container class="content">
    <el-header class="header">
      <el-row>
        <el-col :span="8" class="header_one">
          <p>matata</p>
        </el-col>
        <el-col :span="8" class="header_two">
          <p>电商后台管理系统</p>
        </el-col>
        <el-col :span="8" class="header_three">
          <a href="#">退出</a>
        </el-col>
      </el-row>
    </el-header>
    <el-container>
      <el-aside class="aside" width="200px">
        <el-menu
          default-active="2"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose"
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-s-custom"></i>
              <span>导航一</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">选项1</el-menu-item>
            </el-menu-item-group>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main class="main">Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {};
</script>

<style>
.content {
  height: 100%;
}
.header {
  height: 150px;
  background-color: #b3c0d1;
}
.aside {
  background-color: #d3dce6;
}
.main {
  background-color: #e9eef3;
}
.header_one {
  font-weight: bold;
  font-size: 40px;
  text-align: center;
  justify-content: center;
}
.header_two {
  font-weight: bold;
  font-size: 40px;
  text-align: center;
  justify-content: center;
}
.header_three {
  font-size: 20px;
  line-height: 60px;
  text-align: center;
}
</style>
