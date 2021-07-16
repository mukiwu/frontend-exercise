<template>
  <div>
    
      <div class="nav btn-group" id="v-pills-tab" role="tablist">
        <button class="btn btn-outline-primary active" data-bs-toggle="tab" data-bs-target="#v-pills-home" type="button" role="tab">Home</button>
        <button class="btn btn-outline-primary" data-bs-toggle="tab" data-bs-target="#v-pills-profile" type="button" role="tab">Profile</button>
        <button class="btn btn-outline-primary" data-bs-toggle="tab" data-bs-target="#v-pills-messages" type="button" role="tab">Messages</button>
        <button class="btn btn-outline-primary" data-bs-toggle="tab" data-bs-target="#v-pills-settings" type="button" role="tab">Settings</button>
      </div>
      <div class="tab-content" id="v-pills-tabContent">
        <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel">123</div>
        <div class="tab-pane fade" id="v-pills-profile" role="tabpanel">456</div>
        <div class="tab-pane fade" id="v-pills-messages" role="tabpanel">789</div>
        <div class="tab-pane fade" id="v-pills-settings" role="tabpanel">000</div>
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
