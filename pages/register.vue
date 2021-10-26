<template>
  <div class="login-container">
    <el-form class="login-form" label-width="100px" :model="form" :rules="rules" ref="registerForm">
      <div class="title-container">
        <img src="/logo.jpg" alt="">
      </div>
      <el-form-item prop="email" label="邮箱">
        <el-input v-model="form.email" placeholder="请输入邮箱"></el-input>
      </el-form-item>
      <el-form-item prop="captcha" label="验证码" class="captcha-container">
        <div class="captcha">
          <img :src="code.captcha" alt="">
        </div>
        <el-input v-model="form.captcha" placeholder="请输入验证码"></el-input>
      </el-form-item>
      <el-form-item prop="nickname" label="昵称">
        <el-input v-model="form.nickname" placeholder="请输入昵称"></el-input>
      </el-form-item>
      <el-form-item prop="passwd" label="密码">
        <el-input v-model="form.passwd" placeholder="请输入密码"></el-input>
      </el-form-item>
      <el-form-item prop="repasswd" label="确认密码">
        <el-input v-model="form.repasswd" placeholder="请再次输入密码"></el-input>
      </el-form-item>
      <el-form-item label=" ">
        <el-button type="primary" size="default">注册</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  layout: 'login',
  data() {
    return {
      form: {
        email: '',
        nickname: '',
        passwd: '',
        repasswd: ''
      },
      rules: {
        email: [{
          required: true, message: '请输入邮箱'
        }, {
          type: 'email', message: '请输入正确的邮箱格式'
        }],
        nickname: [{
          required: true, message: '请输入昵称'
        }]
      },
      code: {
        captcha: '/api/captcha'
      }
    }
  },
}
</script>

<style>

</style>