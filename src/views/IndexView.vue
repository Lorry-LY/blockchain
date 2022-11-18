<template>
    <div class="index">
        <MenuBar/>
        <OfficialIndex/>
    </div>
</template>

<script>
// @ is an alias to /src
import OfficialIndex from '@/components/OfficialIndex.vue'
import MenuBar from '@/components/navBar/NavBar.vue'

export default {
  name: 'IndexView',
  components: {
    MenuBar,
    OfficialIndex
  }
}
</script>

<style scoped>
.index {
  width: 100%;
  height: 100%;
}

</style>
