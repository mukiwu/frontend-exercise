<template>
  <div class="col my-2">
    <div class="card">
      <a href="#" class="d-inline-block text-end pt-2 pe-3" @click.prevent="updateStatus(data.
        SiteName)">
        <div v-show="parentStar.indexOf(data.SiteName) == -1"><font-awesome-icon :icon="['far', 'star']" />
  </div>
        <div v-show="parentStar.indexOf(data.SiteName) !== -1"><font-awesome-icon icon="star" />
  </div>
      </a>
      <div class="card-body">
        <div class="text-center mb-2"><h3>{{ data.County }}</h3></div>
        <div class="d-flex justify-content-center">
          <div class="text-center mx-2"><h4 class="mb-0">{{ data.AQI }}</h4><span class="badge bg-secondary">AQI 指數</span></div>
          <div class="text-center mx-2"><h4 class="mb-0">{{ data['PM2.5'] }}</h4><span class="badge bg-secondary">PM2.5</span></div>
        </div>
        <div class="text-center mt-3">
          <div class="badge" :class="status(data.Status)">{{ data.Status }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cardComponent",
  props: {
    data: {
      type: Object
    },
    parentStar: {
      type: Array
    },
    filter: {
      type: String
    }
  },
  data() {
    return {
      // star: this.parentStar
    }
  },
  methods: {
    status(e) {
      switch(e) {
        case '普通':
          return 'bg-info'
        case '對敏感族群不健康':
          return 'bg-warning'
        case '對所有族群不健康':
          return 'bg-warning'
        case '非常不健康':
          return 'bg-danger'
        case '危害':
          return 'bg-danger'
        default: 
          return 'bg-dark'
      }
    },
    updateStatus(siteName) {
      this.$emit('star', siteName)
    }
  }
}
</script>

<style scoped lang="scss">
.card {
  background: linear-gradient(135deg,#eee,#fcfcfc);
  border: 1px solid #e5e5e5;
}

</style>
