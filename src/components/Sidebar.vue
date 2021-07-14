<template>
  <div>
    <p class="my-5">總共有 2 個作品</p>
    <div class="card">
      <div class="card-header">
        程式語言
      </div>
      <div class="card-body">
        <div class="form-check mb-1">
          <input class="form-check-input" type="checkbox" value="" id="vueCheck">
          <label class="form-check-label" for="vueCheck">
            VueJs
          </label>
        </div>
        <div class="form-check mb-1">
          <input class="form-check-input" type="checkbox" value="" id="bootstrapCheck">
          <label class="form-check-label" for="bootstrapCheck">
            Bootstrap
          </label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
