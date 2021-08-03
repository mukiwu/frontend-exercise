<template>
  <div>
    <div class="d-flex justify-content-end my-5">
      <div class="nav btn-group" role="tablist">
        <button class="btn btn-outline-danger active" data-bs-toggle="tab" data-bs-target="#tabGrid" type="button" role="tab"><font-awesome-icon icon="th-large" /></button>
        <button class="btn btn-outline-danger" data-bs-toggle="tab" data-bs-target="#tabList" type="button" role="tab"><font-awesome-icon icon="list" /></button>
      </div>
      
    </div>
    <div class="tab-content">
      <div class="tab-pane fade show active" id="tabGrid" role="tabpanel">
        <div class="d-flex justify-content-between">
          <div class="card" v-for="(item, key) in exercise" :key="key">
            <div class="card-header">
              {{ item.name }}
            </div>
            <div class="card-body">
              <img src="https://picsum.photos/300/200" alt="">
            </div>
            <div class="card-footer">
              <span class="badge bg-danger me-1" v-for="(tag, key) in item.tags" :key="key">
                {{ tag }}
              </span>
            </div>
          </div>
        </div>
      </div>
      <div class="tab-pane fade" id="tabList" role="tabpanel">456</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Main',
  data() {
    return {
      exercise: [
        { name: '待辦事項 ToDo List',
          tags: ["vue", "css", "html"]
        },{
          name: '城市環境資源篩選器',
          tags: ["vue", "JS"]
        }
      ]
    }
  }
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
