<template>
  <div class="col my-2">
    <div class="card">
      <div class="card-body">
        <div class="d-flex justify-content-between">
          <h2 class="mb-5">{{ data.County }}
          </h2>
          <a href="#" class="star pt-2 pe-2" @click.prevent="updateStatus(data.
        SiteName)">
            <div v-show="parentStar.indexOf(data.SiteName) == -1"><font-awesome-icon :icon="['far', 'star']" />
      </div>
            <div v-show="parentStar.indexOf(data.SiteName) !== -1"><font-awesome-icon icon="star" />
      </div>
          </a>
        </div>
        <div class="card-info pb-2">最後更新時間：<br />{{ data.PublishTime }}</div>
      </div>
      <div class="card-footer p-0">
        <div class="d-flex justify-content-between">
          <div class="left">
            <div class="d-flex justify-content-between pt-3 ps-5 pe-3">
              <h4>{{ data.AQI }}</h4><span class="badge text-des">AQI 指數</span>
            </div>
            <div class="d-flex justify-content-between pt-1 pb-2 ps-5 pe-3">
              <h4>{{ data['PM2.5'] }}</h4><span class="badge text-des">PM2.5</span>
            </div>
          </div>
          <div class="right d-flex align-items-center justify-content-center">
            <div :class="status(data.Status)">{{ data.Status }}</div>
          </div>
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
      type: Object,
    },
    parentStar: {
      type: Array,
    },
    filter: {
      type: String,
    },
  },
  data() {
    return {
      // star: this.parentStar
    };
  },
  methods: {
    status(e) {
      switch (e) {
        case "普通":
          return "text-info";
        case "對敏感族群不健康":
          return "text-warning";
        case "對所有族群不健康":
          return "text-warning";
        case "非常不健康":
          return "text-danger";
        case "危害":
          return "text-danger";
        default:
          return "text-dark";
      }
    },
    updateStatus(siteName) {
      this.$emit("star", siteName);
    },
  },
};
</script>

<style scoped lang="scss">
h2 {
  color: #fff;
  font-weight: 300;
}

a.star {
  color: #fff;
}

.card {
  background: linear-gradient(135deg, #808ca5, #57688f);
}

.card-info {
  color: #fff;
  font-size: 0.8em;
}

.left {
  background: #fff;
  width: 70%;
  color: #a5a5af;
}

.text-des {
  color: #a5a5af;
  padding: .65em !important;
}

.right {
  background: #dee7e7;
  width: 30%;
}

</style>
