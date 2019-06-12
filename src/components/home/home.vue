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
          <a @click.prevent="signout()" class='signout' href="">退出</a>
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
              <span>用户管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                <i class="el-icon-s-grid"></i>
                <span>用户列表</span>
              </el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title">
              <i class="el-icon-s-custom"></i>
              <span>权限管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                <i class="el-icon-s-grid"></i>
                <span>角色列表</span>
              </el-menu-item>
              <el-menu-item index="1-2">
                <i class="el-icon-s-grid"></i>
                <span>权限列表</span>
              </el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title">
              <i class="el-icon-s-custom"></i>
              <span>商品管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                <i class="el-icon-s-grid"></i>
                <span>商品列表</span>
              </el-menu-item>
              <el-menu-item index="1-2">
                <i class="el-icon-s-grid"></i>
                <span>分类参数</span>
              </el-menu-item>
              <el-menu-item index="1-3">
                <i class="el-icon-s-grid"></i>
                <span>商品分类</span>
              </el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="4">
            <template slot="title">
              <i class="el-icon-s-custom"></i>
              <span>订单管理</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                <i class="el-icon-s-grid"></i>
                <span>订单列表</span>
              </el-menu-item>
            </el-menu-item-group>
          </el-submenu>
          <el-submenu index="5">
            <template slot="title">
              <i class="el-icon-s-custom"></i>
              <span>数据统计</span>
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">
                <i class="el-icon-s-grid"></i>
                <span>数据列表</span>
              </el-menu-item>
            </el-menu-item-group>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main class="main">Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  beforeCreate(){
    const token = localStorage.getItem('token')

    if(!token){
      this.$router.push({name:'login'})
    }
  },
  methods:{
    signout(){
      //清除token值
      localStorage.clear()
      //提示框
      this.$message.success('退出成功')
      //来到登录页
      this.$router.push({name:'login'})

    }
  }
};
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
