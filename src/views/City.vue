<template>
  <div id="app" class="container">
    <select name="" id="" class="form-control mb-3" v-model="filter">
      <option value="">--- 請選擇城市 ---</option>
      <option v-for="(item, key) in location" :key="key" :value="item">{{ item }}</option>
    </select>
    <div>
      <h4>關注城市</h4>
      <div class="row row-cols-3">
        <card-component v-for="(item, key) in starAQIData()" v-on:star="starStatus" :data="item" :key="key" :parent-star="stared"></card-component>
      </div>
    </div>
    
    <hr>
    <h4>一般城市</h4>
    <div class="row row-cols-3">
      <card-component v-for="(item, key) in filterAQIData(filter)" v-on:star="starStatus" :data="item" :key="key" :parent-star="stared" :filter="filter"></card-component>
    </div>
  </div>
</template>


<script>
import cardComponent from '@/components/cardComponent.vue'

// API 來源
// https://opendata.epa.gov.tw/Data/Contents/AQI/

export default {
  name: 'City',
  data() {
    return {
      AQIdata: [],
      stared: [],
      location: ['臺北市','新北市','基隆市','桃園市','新竹市','新竹縣','苗栗縣','臺中市','彰化縣','南投縣','雲林縣','嘉義市','嘉義縣','臺南市','高雄市','屏東縣','宜蘭縣','花蓮縣','臺東縣','澎湖縣','金門縣','連江縣'],
      filter: '',
      attention: false
    }
  },
  components: {
    "card-component": cardComponent,
  },
  created: function() {
    this.getData()
    if (localStorage.getItem("stared") !== null) {
      this.stared = JSON.parse(localStorage.getItem("stared"))
    }
    
  },
  methods: {
    getData() {
      const vm = this
      const api = 'http://opendata2.epa.gov.tw/AQI.json';
			// https 環境下是禁止取得 http 資源
			// 可以將資源改成使用 https://cors-anywhere.herokuapp.com/ + url
			// 透過 cors-anywhere.herokuapp 協助取得 http 資源，然後轉為 https 供運用

      vm.$http.get(api).then(response => {
        vm.AQIdata = response.data
        console.log(vm.AQIdata)
      });
    },
    starStatus(val) {
      let index = this.stared.indexOf(val)
      if(index === -1) {
        this.stared.push(val)
      } else {
        this.stared = this.stared.filter(function(obj) {
          return obj !== val
        })
      }
      localStorage.setItem('stared', JSON.stringify(this.stared))
    },
    starAQIData() {
      let vm = this
      return vm.AQIdata.filter(obj => {
        return vm.stared.indexOf(obj.SiteName) !== -1
      })
    },
    filterAQIData(filter) {
      let vm = this
      return vm.AQIdata.filter(obj => {
        return obj.County.indexOf(filter)!== -1
      })
    }
  }
}
</script>
