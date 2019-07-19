<template>
  <div>
    <div class="login-tong">
      <div class="login-phones" for="phone">
        手机号码：
      </div>
      <input v-model="a" type="text" id="phone" class="login-phone" placeholder="请输入手机号码...">
    </div>
    <div>
      <div class="login-phones" for="phone">
        验证码：
      </div>
      <input type="text" id="phone" class="login-phone" placeholder="请输入验证码...">
    </div>
    <button @click="yanzhengma">发送验证码</button>
    <button @click="addgai">登录</button>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        a: "",
        b: ""

      }
    },
    methods: {
      getRandomColor() {
        let rgb = []
        for (let i = 0; i < 3; ++i) {
          let color = Math.floor(Math.random() * 256).toString(16)
          color = color.length == 1 ? '0' + color : color
          rgb.push(color)
        }
        return '#' + rgb.join('')
      },
      yanzhengma() {
        console.log(this.a)
        mpvue.request({
          url: 'https://wangzw.club:1999/react//sendCode', //仅为示例，并非真实的接口地址
          method: "POST",
          data: {
            mobile: this.a
          },
          header: {
            'content-type': 'application/json' // 默认值
          },
          success: (res) => {
            console.log(res.data.result)
            this.b = res.data.result
          }
        })
      },
      addgai() {
        mpvue.request({
          url: 'https://wangzw.club:1999/react/checkCode', //仅为示例，并非真实的接口地址
          method: "POST",
          data: {
            mobile: this.a,
            code: this.b
          },
          header: {
            'content-type': 'application/json' // 默认值
          },
          success(res) {
            console.log(res.data)
            if (!!res.data.type) {
              console.log(1110)
              wx.switchTab({
                url: '../index/main'
              })
            }
          }
        })
      }
    }
  }
</script>
<style>

</style>