<template>
  <div class="content">
    <el-steps :active="activeStep" finish-status="success" align-center style="margin-bottom:20px;">
      <el-step v-for="(item,index) in steps" :title="item" :key="index"></el-step>
    </el-steps>

    <el-form v-show="activeStep == 0" :model="companyInfo" :rules="rules" ref="BasicForm" label-width="150px"
      class="demo-ruleForm">
      <el-form-item label="公司名称" prop="name">
        <el-input v-model="companyInfo.name"></el-input>
      </el-form-item>
      <el-form-item label="公司区域社会统一信用代码（18位）" prop="code">
        <el-input v-model="companyInfo.code"></el-input>
      </el-form-item>
      <el-form-item label="超级用户名" prop="username">
        <el-input v-model="companyInfo.username"></el-input>
      </el-form-item>
      <el-form-item label="超级用户密码" prop="password">
        <el-input v-model="companyInfo.password" type="password"></el-input>
      </el-form-item>
      <el-form-item label="确认密码" prop="pass_sure">
        <el-input v-model="pass_sure" type="password"></el-input>
      </el-form-item>
      <el-button style="margin-top: 12px;" @click="submitForm('BasicForm')" type="primary">下一步</el-button>
    </el-form>

    <div v-show="activeStep == 1" class="sureForm">
      <div class="text_line">公司名称：{{companyInfo.name}}</div>
      <div class="text_line">超级管理员：{{companyInfo.username}}</div>
      <div class="text_line">公司区域社会统一信用代码:<br>{{companyInfo.code}}</div>
      <div>
        <el-button style="margin-top: 12px;margin-right: 20px;" @click="previousStep" type="primary">返回修改</el-button>
        <el-button style="margin-top: 12px;" @click="register" type="success">注册</el-button>
      </div>
    </div>

  </div>
</template>


<script>
export default {
  data() {
    var sure_password = (rule, value, callback) => {
      if (this.pass_sure === '') {
        callback(new Error('请再次输入密码'))
      } else if (this.pass_sure !== this.companyInfo.password) {
        callback(new Error('两次输入密码不一致!'))
      } else {
        callback()
      }
    }
    return {
      companyInfo: {
        name: '',
        code: '',
        username: '',
        password: ''
      },
      rules: {
        name: [
          { required: true, message: '请输入公司名称', trigger: 'blur' },
        ],
        code: [
          { required: true, message: '请输入统一信用代码', trigger: 'blur' },
          { min: 18, max: 18, message: '信用码不合法', trigger: 'blur' }
        ],
        username: [
          { required: true, message: '请输入超级用户名', trigger: 'blur' },
        ],
        password: [
          { required: true, message: '请输入超级用户密码', trigger: 'blur' },
          { min: 8, max: 50, message: '长度在 8 到 50 个字符', trigger: 'blur' }
        ],
        pass_sure: [
          { required: true, validator: sure_password, trigger: 'blur' },
        ],
      },
      pass_sure: '',
      steps : ['输入信息','确认信息'],
      activeStep: 0
    }
  },
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate((valid) => {
        if (valid) {
          this.activeStep++;
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    register() {
      
    },
    resetForm(formName) {
      this.$refs[formName].resetFields();
    },
    nextStep() {
      this.activeStep++;
    },
    previousStep() {
      this.activeStep--;
    }
  }
}
</script>

<style scoped>

.demo-ruleForm {
  width: 50%;
  margin: auto;
}

.text_line{
  font-size: 20px;
  text-align: left;
  width: 200px;
  margin: 20px auto;
}
</style>