<template>
  <div id="app">
    <div class="header py-5">
      <div class="container-xl">
        <div class="row">
          <div class="col">
            <router-link to="/"><h1>MUKI wu / Portfolio</h1></router-link>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <div class="row my-5">
        <div class="col-md-3">
          <Sidebar />
        </div>
        <div class="col-md-9">
          <router-view/>
        </div>
      </div>
    </div>
    
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    
  </div>
</template>

<script>
import Sidebar from '@/components/Sidebar.vue'

export default {
  components: {
    Sidebar,
  }
}
</script>

<style lang="scss">
body {
  background: #edeef3;
}

#app {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
}

.header {
  background: #c1c8d6;
  h1 {
    font-weight: 300;
    color: #333;
  }
  a {
    color: #fff;
    text-decoration: none;
  }
}

// Bootstrap Setting

@media (min-width: 1400px) {
  .container, .container-lg, .container-md, .container-sm, .container-xl, .container-xxl {
      max-width: 1140px;
  }
}
</style>
