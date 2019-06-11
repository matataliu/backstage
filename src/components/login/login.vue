<template>
  <div class="login">
    <el-form class="login_warp" label-position="top" label-width="80px" :model="formdata">
      <h1>用户登录</h1>
      <el-form-item label="用户名">
        <el-input v-model="formdata.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="formdata.password"></el-input>
      </el-form-item>
      <el-button 
      @click.prevent="Login()"
      class="login_btn" type="primary" round>登录</el-button>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      labelPosition: "right",
      formdata: {
        username: "",
        password: ""
      }
    };
  },
  methods:{
      //登陆请求
    Login() {
        this.$http.post('login',this.formdata).then((res)=>{
            const {
                data,
                meta:{msg,status}
            } = res.data

            if(status===200){
                this.$router.push({name:'home'})
                this.$message.success(msg);
            }else{
                this.$message.warning(msg);
            }
        })
    }
  }
};
</script>

<style>

.login{
    height: 100%;
    background-color:#324152;
    display: flex;
    justify-content: center;
    align-items: center;
}
.login_warp h1{
    font-size: 30px;
    font-weight: bold;
}
.login_warp{
    width: 400px;
    background-color: #fff;
    border-radius: 5px;
    padding: 30px;
}
.login_btn{
    width: 100%;
}
</style>
