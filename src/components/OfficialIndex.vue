<template>
  <div class="content">
    <el-row type="flex" class="row-bg" justify="center">
      <el-col :span="10">
        <div class="grid-content bg-purple">
          <transition name="el-fade-in-linear">
            <div v-show="show" class="text">
              <div class="title">
                区块链产品信息管理系统
              </div>
              <div class="introduce">
                基于区块链技术的产品流水线信息管理技术，为企业打造统一、丰富的信息管理平台，为产品溯源
                提供可行性的解决方案
              </div>
              <el-button @click="gotoRegister" class="btn" type="primary" route="/register">加入我们</el-button>
              <!-- <div class="vedio_content">
                <el-button class="btn1" :icon="Search" circle />
                查看详细介绍
              </div> -->
            </div>
          </transition>
        </div>
      </el-col>
      <el-col :span="10">
        <transition name="el-fade-in">
          <div v-show="show" class="grid-content bg-purple-light">
            <!-- <el-image fit="fill" placeholder="图片正在加载。。" error="图片加载失败" key="index.png" src="../assets/index.png" alt="我的图片不在了" lazy></el-image> -->
            <img class="image" placeholder="图片正在加载" src="../assets/login/index.png" />
          </div>
        </transition>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 1,
      show:true
    }
  },
  methods: {
    gotoRegister(event) {
      this.$router.push('register')
    }
  }
}
</script>

<style scoped>
.content {
  position: absolute;
  width: 100%;
  height: 100%;
}

.el-row {
  height: 100%;
  margin-bottom: 20px;
}

.btn {
  position: absolute;
  width: 160px;
  height: 60px;
  background: #5a4fdc;
  left: 5%;
  margin: 30px auto;
}

.btn1 {
  position: absolute;
  width: 80px;
  height: 80px;
  left: 5%;
  background: transparent;
  border-block: #000;
}

.vedio_content {
  padding-top: 40%;
  width: 100%;
  text-align: left;
}

.text {
  position: absolute;
  width: 60%;
  height: 70%;
  top: 20%;
  left: 0;
  right: -2%;
  bottom: 0;
  margin: auto;
}

.title {
  font-size: 3em;
  margin: 30px auto;
  text-align: left;
}

.introduce {
  font-size: 1em;
  margin: 30px auto;
  text-align: left;
}

.image {
  position: absolute;
  /* width: 80%;
    height: 100%; */
  top: 0;
  left: -20%;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 1000px;
  height: 700px;
}

.el-col {
  border-radius: 4px;
}

.bg-purple-dark {
  background: transparent;
}

.bg-purple {
  background: transparent;
}

.bg-purple-light {
  background: transparent;
}

.grid-content {
  position: relative;
  border-radius: 4px;
  min-height: 36px;
  height: 100%;
}
</style>
