<template>
  <div id="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
    <home-swiper :banners="banners"></home-swiper>
    <recommend-view :recommends="recommends"></recommend-view>
    <div class="bzlx"><h3>本周流行</h3></div>
    <feature-view :recommends="recommends"></feature-view>
    <feature-view :recommends="recommends"></feature-view>
    <tab-control
      class="tab-control"
      :titles="['流行', '新款', '精选']"
    ></tab-control>
  </div>
</template>

<script>
import HomeSwiper from "./childComps/HomeSwiper";
import RecommendView from "./childComps/RecommendView";
import FeatureView from "./childComps/FeatureView";

import NavBar from "common/navbar/NavBar";
import TabControl from "content/tabControl/TabControl";

import { getHomeMultidata, getHomeGoods } from "network/home";

export default {
  name: "Home",
  components: {
    HomeSwiper,
    RecommendView,
    FeatureView,
    NavBar,
    TabControl,
  },
  data() {
    return {
      banners: [],
      recommends: [],
      goods: {
        pop: { page: 0, list: [] },
        new: { page: 0, list: [] },
        sell: { page: 0, list: [] },
      },
    };
  },
  created() {
    this.getHomeMultidata();
    this.getHomeGoods("pop");
    this.getHomeGoods('new')
    this.getHomeGoods('sell')
  },
  methods: {
    getHomeMultidata() {
      getHomeMultidata().then((res) => {
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommend.list;
      });
    },
    getHomeGoods(type) {
      const page = this.goods[type].page + 1;
      getHomeGoods(type, page).then((res) => {
        // this.goods[type].list.push(...res.data.list);
        this.goods[type].page += 1;
      });
    },
  },
};
</script>

<style scoped>
#home {
  height: 2000px;
}
.home-nav {
  /* background-color: rgb(213, 44, 143); */
  background-color: rgba(213, 44, 143, 0.3);
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 999;
}
.tab-control {
  position: sticky;
  top: 44px;
}
.bzlx {
  text-align: center;
  padding: 10px 0 10px;
}
</style>
