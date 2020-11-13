<template>
  <div id="category">
    <category-nav></category-nav>
  </div>
</template>

<script>

import CategoryNav from "./childComps/CategoryNav";



export default {
  name: "Category",
  components: {
    CategoryNav,

  },
};
</script>

<style scoped>
#category {
  height: 2000px;
}


</style>
