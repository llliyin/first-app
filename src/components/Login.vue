<template>
  <div class="container">
  <group title="用户登录">
      <x-input title="手机号" mask="999 9999 9999" v-model="phone" :max="13" ></x-input>
      <x-input title="登录密码" type="password" v-model="password" :max="13"></x-input>
  </group>
    <div class="btn">
      <x-button @click.native="login">登录</x-button>
    </div>
  </div>
</template>

<script>
import { Group, Cell, XInput, XButton, Alert, AlertModule } from 'vux'

export default {
  components: {
    Group,
    Cell,
    Alert,
    XInput,
    XButton
  },
  methods: {
    login () {
      if (this.password === '123456') {
        this.$router.push({ path: '/' })
      } else {
        AlertModule.show({
          title: '登录失败',
          content: '密码错误'
        })
      }
    }
  },
  data () {
    return {
      phone: '12345678978',
      password: ''
    }
  }
}
</script>

<style>
.btn {
  margin: 10pt
}
.container {
  background-color: aquamarine
}
</style>
