<template>
  <div>
    <div class="card">
      <div class="card-header py-3">
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
.card {
  border: 1px solid #e5e5e5;
}

.card-header {
  background: #fff;
  border-bottom: 1px solid #eee;
}
</style>
