<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
  <div class="container">
    <div class="row my-5">
      <div class="col-md-3">
        <Sidebar />
      </div>
      <div class="col-md-9">
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
