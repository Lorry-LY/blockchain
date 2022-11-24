<template>
  <!-- <el-menu
    :default-active="this.$router.path"
    class="el-menu-demo"
    mode="horizontal"
    :ellipsis="false"
    router
  >
    <div class="flex-grow" />
    <el-menu-item index="/">我们主页</el-menu-item>
    <div class="flex-grow" />
    <el-sub-menu index="2">
      <template #title>产品介绍</template>
      <el-menu-item index="2-1">item one</el-menu-item>
      <el-menu-item index="2-2">item two</el-menu-item>
      <el-menu-item index="2-3">item three</el-menu-item>
      <el-sub-menu index="2-4">
        <template #title>item four</template>
        <el-menu-item index="2-4-1">item one</el-menu-item>
        <el-menu-item index="2-4-2">item two</el-menu-item>
        <el-menu-item index="2-4-3">item three</el-menu-item>
      </el-sub-menu>
    </el-sub-menu>
    <el-sub-menu index="3">
      <template #title>产品支持</template>
      <el-menu-item index="3-1">item one</el-menu-item>
      <el-menu-item index="3-2">item two</el-menu-item>
      <el-menu-item index="3-3">item three</el-menu-item>
    </el-sub-menu>
    <div class="flex-grow" />
    <el-menu-item index="3" disabled>打开控制台</el-menu-item>
    <el-menu-item index="/login">登录</el-menu-item>
    <div class="flex-grow" />
  </el-menu> -->
  <el-menu router :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="/" key="1" class="index_item">我的主页</el-menu-item>
    <el-submenu index="2" key="2" class="product_item">
      <template slot="title">产品列表</template>
      <el-menu-item index="/product">产品1</el-menu-item>
      <el-menu-item index="/product">产品2</el-menu-item>
      <el-menu-item index="/product">产品3</el-menu-item>
    </el-submenu>
    <el-submenu index='3' key="3" class="intro_item">
      <template slot="title">关于我们</template>
      <el-menu-item index="/team">团队介绍</el-menu-item>
      <el-menu-item index="/join">打入我们</el-menu-item>
    </el-submenu>
    <el-menu-item index="3" disabled class="control_item">控制台</el-menu-item>
    <el-menu-item index="/login" class="login_item">登录</el-menu-item>
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '/',
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        this.activeIndex = key
        console.log(key, keyPath);
      }
    }
  }
</script>

<style scoped>
.flex-grow {
  flex-grow: 1;
}

.el-menu-demo{
  position:absolute;
  left: 0;
  top: 0;
  float: left;
  width: 100%;
  z-index: 1;
  background: transparent;
}

.index_item{
  margin-left: 15% !important;
}

.product_item{
  margin-left: 20% !important;
}

.intro_item {
  margin-left: 2% !important;
}

.control_item {
  margin-left: 20% !important;
}

.login_item{
  margin-left: 2% !important;
}
</style>
