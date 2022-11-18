<template>
  <div class="index">
    <MenuBar class="navbar"/>
    <div class="content">
      <LoginForm class="loginForm"/>
    </div>
  </div>
</template>

<script>
import LoginForm from '@/components/form/LoginForm.vue'
import MenuBar from '@/components/navBar/NavBar.vue'
export default {
name: 'LoginView',
components: {
  MenuBar,
  LoginForm
}
}
</script>

<style scoped>
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
background: url(../assets/login/web5.jpg) no-repeat;
background-size:cover;
}

.loginForm {
position: absolute;
  width: 20%;
  height: min-content;
  top: 0;
  right: 10%;
  bottom: 0;
  margin: auto;
}

</style>
