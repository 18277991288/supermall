<template>
  <div><nav-bar class="category-nav">
      <div slot="left" class="category-scan"><img src="~assets/img/category/scan.png" alt=""><p>扫描</p></div>
      <div slot="center" ><input type="text" placeholder="  保暖服饰 2折狂欢"/></div>
      <div slot="right" class="category-message"><img src="~assets/img/category/message.png" alt=""><p>消息</p></div></nav-bar
    ></div>
</template>

<script>
import NavBar from "common/navbar/NavBar";

export default {
  name: "CategoryNav",
  components: {
    NavBar,
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
.category-nav {
  background-color:#fff;
  color: black;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 999;
}
.category-nav input {
  height: 22px;
  width: 200px;
   border-radius: 10px;
   background: rgb(246, 246, 246);
   border: none;
   outline-color: rgb(113, 113, 113);
   font-size: 8px;
}
.category-scan{
  position: relative;
}
.category-scan img{
  height: 16px;
  width: 16px;
  position: absolute;
  top: 7px;
  left: 33px;

}
.category-scan p {
  font-size: 6px;
  position: absolute;
  top: 11px;
  left: 29px;
}
.category-message{
  position: relative;
}
.category-message img{
  height: 22px;
  width: 22px;
  position: absolute;
  top: 7px;
  left: 10px;

}
.category-message p {
  font-size: 6px;
  position: absolute;
  top: 12px;
  left: 10px;
}
</style>
