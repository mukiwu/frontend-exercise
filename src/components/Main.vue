<template>
  <div>
    <div class="d-flex justify-content-end">
      <div class="nav btn-group" role="tablist">
        <button class="btn btn-outline-danger active" data-bs-toggle="tab" data-bs-target="#tabGrid" type="button" role="tab"><font-awesome-icon icon="th-large" /></button>
        <button class="btn btn-outline-danger" data-bs-toggle="tab" data-bs-target="#tabList" type="button" role="tab"><font-awesome-icon icon="list" /></button>
      </div>
      
    </div>
    <div class="tab-content">
      <div class="tab-pane fade show active" id="tabGrid" role="tabpanel">123</div>
      <div class="tab-pane fade" id="tabList" role="tabpanel">456</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Main'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.nav {
  .btn {
    font-size: .8em;
  }
}
</style>
