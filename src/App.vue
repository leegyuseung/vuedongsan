<template>
  <!-- 모달 -->
  <ModalContent
    :products="products"
    :clickData="clickData"
    :modalHandler="modalHandler"
    @closeModal="modalHandler = false"
  />

  <!-- nav -->
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <!-- 배너 -->
  <DiscountBanner />

  <!-- 상품 -->
  <CardItem
    @openModal="
      modalHandler = true;
      clickData = $event;
    "
    :products="products[i]"
    v-for="(product, i) in products"
    :key="i"
  />
</template>

<script>
import data from "./assets/data";
import DiscountBanner from "./components/DiscountBanner.vue";
import ModalContent from "./components/ModalContent.vue";
import CardItem from "./components/CardItem.vue";

export default {
  name: "App",
  data() {
    return {
      clickData: 0,
      modalHandler: false,
      count: [0, 0, 0],
      menus: ["Home", "Products", "About"],
      products: data,
    };
  },
  components: { DiscountBanner, ModalContent, CardItem },
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
