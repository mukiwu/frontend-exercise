<template>
  <div>
    <div class="d-flex justify-content-end">
      <div class="nav btn-group" role="tablist">
        <button class="btn btn-outline-primary active" data-bs-toggle="tab" data-bs-target="#tabGrid" type="button" role="tab"><span class="fe fe-grid"></span></button>
        <button class="btn btn-outline-primary" data-bs-toggle="tab" data-bs-target="#tabList" type="button" role="tab">Profile</button>
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
