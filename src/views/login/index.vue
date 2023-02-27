<template>
  <div class="login">
    <el-form ref="form" label-position="top" :model="form" label-width="80px" class="login-form">
      <el-form-item label="手机号">
        <el-input v-model="form.phone"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="form.password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button class="login-btn" type="primary" @click="onSubmit">立即创建</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import request from '@/utils/request'
import qs from 'qs'

export default Vue.extend({
  name: 'LoginIndex',
  data () {
    return {
      form: {
        phone: '18201288771',
        password: '111111'
      }
    }
  },
  methods: {
    async onSubmit () {
      console.log('submit!')
      const { data } = await request({
        method: 'POST',
        url: '/front/user/login',
        headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
        data: qs.stringify(this.form)
      })
      console.log(data)
    }
  }
})
</script>

<style lang="scss" scoped>
  .login {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    .login-form {
      width: 300px;
      background: #fff;
      padding: 20px;
      border-radius: 5px;
    }
    .login-btn {
      width: 100%;
    }
  }
</style>
