<template>
  <div class="card" :class="status(data.Status)">
    <div class="card-header">{{ data.County }}
      <a href="#" class="float-right" @click.prevent="updateStatus(data.
      SiteName)">
        <div v-show="parentStar.indexOf(data.SiteName) == -1"><font-awesome-icon :icon="['far', 'star']" />
</div>
        <div v-show="parentStar.indexOf(data.SiteName) !== -1"><font-awesome-icon icon="star" />
</div>
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
          return 'status-aqi2'
        case '對敏感族群不健康':
          return 'status-aqi3'
        case '對所有族群不健康':
          return 'status-aqi4'
        case '非常不健康':
          return 'status-aqi5'
        case '危害':
          return 'status-aqi6'
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

<style scoped lang="scss">
/*
狀態對應表
'良好',
'status-aqi2' '普通',
'status-aqi3' '對敏感族群不健康',
'status-aqi4' '對所有族群不健康',
'status-aqi5' '非常不健康',
'status-aqi6' '危害'
*/

.status-aqi2 {
  background-color: #ffff00;
}
.status-aqi3 {
  background-color: #ff7e00;
}
.status-aqi4 {
  background-color: #ff0000;
}
.status-aqi5 {
  background-color: #8f3f97;
}
.status-aqi6 {
  background-color: #7e0023;
}
</style>
