<template>
  <div class="card" :class="status(data.Status)">
    <div class="card-header">{{ data.County }}
      <a href="#" class="float-right" @click.prevent="updateStatus(data.
      SiteName)">
        <div v-show="parentStar.indexOf(data.SiteName) == -1"><i class="far fa-star"></i></div>
        <div v-show="parentStar.indexOf(data.SiteName) !== -1"><i class="fas fa-star"></i></div>
      </a>
    </div>
    <div class="card-body">
      <ul class="list-unstyled">
        <li>AQI 指數: {{ data.AQI }}</li>
        <li>PM2.5: {{ data['PM2.5'] }}</li>
        <li>說明: {{ data.Status }}</li>
      </ul>
    {{ data.PublishTime }}
    </div>
  </div>
</template>

<script>
export default {
  template: "#cardComponentTemplate",
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
          return 'status-aqi2'
          break
        case '對敏感族群不健康':
          return 'status-aqi3'
          break
        case '對所有族群不健康':
          return 'status-aqi4'
          break
        case '非常不健康':
          return 'status-aqi5'
          break
        case '危害':
          return 'status-aqi6'
          break
        default: 
          return
      }
    },
    updateStatus(siteName) {
      this.$emit('star', siteName)
    }
  }
}
</script>
