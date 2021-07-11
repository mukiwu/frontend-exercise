<template>
  <div id="app">
    <div class="header">
      <div class="container">
        <div class="row">
          <div class="col">
            <router-link to="/"><h1>Home</h1></router-link>
          </div>
        </div>
      </div>
    </div>
    <router-view/>
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    
  </div>
</template>

<style lang="scss">
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #333;
}

.header {
  background: #d9444a;
  padding: 2rem 0;
  a {
    color: #fff;
    text-decoration: none;
  }
}
</style>
