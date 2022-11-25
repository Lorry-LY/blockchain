<template>
  <div class="login_content">
    <el-tabs v-model="activeName" @tab-click="tabClick">
      <el-tab-pane label="账号密码登录" name="user_passwd">
        <el-form :label-position="labelPosition" label-width="80px" :model="admin">
          <el-form-item label="公司名称">
            <el-input v-model="admin.name" placeholder="公司名称"></el-input>
          </el-form-item>
          <el-form-item label="账号">
            <el-input v-model="admin.username" placeholder="账号或者手机号"></el-input>
          </el-form-item>
          <el-form-item label="密码">
            <el-input v-model="admin.password" type="password" placeholder="密码"></el-input>
          </el-form-item>
        </el-form>
      </el-tab-pane>
      <el-tab-pane label="手机验证码登录" name="phone">
        <el-form :label-position="labelPosition" label-width="80px" :model="admin">
          <el-form-item label="手机号">
            <el-input v-model="admin.phone" placeholder="注册的手机号"></el-input>
          </el-form-item>
            <el-row :gutter="20">
              <el-col :span="16">
                <el-form-item label="验证码">
                  <el-input autocomplete="off" v-model.number="admin.vetify" placeholder="短信验证码"></el-input>
                </el-form-item>
              </el-col>
              <el-col :span="6">
                  <el-button type="primary" class="phone_vetify_btn">获取验证码</el-button>
              </el-col>
            </el-row>
        </el-form>
      </el-tab-pane>
      <el-checkbox v-model="text_checked" class="text_checked">同意协议</el-checkbox> <br>
      <el-button class="vetify_btn">点击验证</el-button><br />
      <el-button class="login_btn" type="primary" :loading="false" :disabled="!text_checked">登录</el-button>
      <br>
      <el-link @click="gotoRegister" type="primary" route="/" style="margin-top: 20px;">没有账号？注册一个</el-link>
    </el-tabs>
  </div>
</template>

<script>

export default {
  data () {
    return {
      text_checked: false,
      activeName: 'user_passwd',
      labelPosition: 'right',
      admin: {
        name: '',
        username: '',
        password: '',
        phone: '',
        vetify: null
      }
    }
  },
  methods: {
    tabClick () {
      this.admin.name = ''
      this.admin.password = ''
      this.admin.phone = ''
      this.admin.vetify = ''
    },
    gotoRegister (event) {
      this.$router.push('register')
    }
  }
}
</script>

<style scoped>
.login_content {
  text-align: left;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.1);
  padding: 20px;
}
.el-form-item {
  margin: 20px auto;
}
.text_checked {
  margin: 20px auto;
}

.vetify_btn {
  width: 100%;
  margin-bottom: 20px;
}

.phone_vetify_btn {
  margin: 20px auto;
}
.login_btn {
  width: 25%;
  margin-left: 37.5%;
}

.el-tabs {
  position: relative;
}
</style>
