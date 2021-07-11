<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
  <div class="container">
    <div class="row">
      <div class="col">
        <Sidebar />
      </div>
      <div class="col">
        <Main />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Sidebar from '@/components/Sidebar.vue'
import Main from '@/components/Main.vue'

export default {
  name: 'Home',
  components: {
    Sidebar,
    Main
  }
}
</script>
