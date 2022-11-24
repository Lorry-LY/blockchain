<template>
  <div class="index">
    <MenuBar class="navbar" />
    <div class="content">
      <RegisterForm class="registerForm" />
    </div>
  </div>
</template>

<script>
import RegisterForm from '@/components/form/RegisterForm.vue'
import MenuBar from '@/components/navBar/NavBar.vue'
export default {
  name: 'LoginView',
  components: {
    MenuBar,
    RegisterForm
  }
}
</script>

<style>
.navbar {
  background-color: #fff;
}

.index {
  height: 100%;
  width: 100%;
}

.content {
  height: 100%;
  width: 100%;
  /* background: url(../assets/login/web5.jpg) no-repeat; */
  background-color: transparent;
  background-size: cover;
}

.registerForm {
  /* position: absolute; */
  width: 70%;
  /* height: min-content;
  top: 20%;
  right: 15%;
  left: 15%; */
  margin: 10% auto auto 0;
  /* margin: auto; */
}
</style>