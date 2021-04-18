<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar-box">
        <img src="../assets/logo.png" alt=""/>
      </div>
      <el-form  ref="loginFormRef" label-width="0px" class="login_form" :model="loginForm" :rules="loginFormRules">
        <el-form-item  prop="username">
          <el-input v-model="loginForm.username" prefix-icon="el-icon-user"></el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input v-model="loginForm.password" prefix-icon="el-icon-lock" type="password"></el-input>
        </el-form-item>
        <el-form-item class="btns">
          <el-button type="primary">登录</el-button>
          <el-button type="info" @click="resetLoginForm">重置</el-button>
        </el-form-item>
        <el-form-item>

        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginForm: {
        username: '',
        password: ''
      },
      loginFormRules: {
        username: [
          {required: true, message: "请输入用户名", trigger: "blur"},
          {min: 3, max: 10, message: "长度在3到10个字符之间", trigger: "blur"}
        ],
        password: [
          {required: true, message: "请输入登录密码", trigger: "blur"},
          {min: 3, max: 10, message: "长度在6到15个字符之间", trigger: "blur"}
        ]
      }
    }
  },
  methods: {
    resetLoginForm() {
      this.$refs
    }
  }
}
</script>

<style lang="less" scoped>
.login_container {
  background-color: #2b4b6b;
  height: 100%;
}

.login_box {
  width: 400px;
  height: 300px;
  background-color: white;
  border-radius: 3px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);

  /*样式嵌套*/

  .avatar-box {
    height: 130px;
    width: 130px;
    border: 3px solid #eee;
    border-radius: 50%;
    padding: 10px;
    box-shadow: 0 0 10px #ddd;
    position: absolute;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;

    img {
      height: 100%;
      width: 100%;
      border-radius: 50%;
      background-color: #eeeeee;
    }
  }
}

.btns {
  display: flex;
  justify-content: center;
}

.login_form{
  position: absolute;
  bottom: 0;
  left: 10%;
  width: 80%;
  padding: 0 20px;
  box-sizing: border-box;
}
</style>
