<template>
  <div class="feature">
    <div v-for="(item, index) in recommends" :key="index" class="feature-item">
      <a :href="item.link">
        <img :src="item.image" alt="" />
        <div>{{ item.title }}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "FeatureView",
  components: {},
  props: {
    recommends: {
      type: Array,
      default() {
        return [];
      },
    },
    data() {
      return {};
    },
  },
};
</script>

<style scoped>
.feature {
  display: flex;
  width: 100%;
  text-align: center;
  font-style: 12px;
  padding: 10px 0 10px;
}

.feature-item {
  flex: 1;
}
.feature-item img {
  width: 75px;
  height: 75px;
  margin-bottom: 10px;
}
</style>
