<template>
  <!-- modal창 -->
  <div class="black-bg" v-if="modalHandler === true">
    <div class="white-bg">
      <h4>{{ products[clickData].title }}</h4>
      <img :src="products[clickData].image" />
      <p>{{ products[clickData].content }}</p>
      <p>{{ products[clickData].price }}</p>
      <button @click="modalHandler = false">닫기</button>
    </div>
  </div>

  <!-- nav -->
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <!-- 상품 -->
  <div v-for="(product, index) in products" :key="index">
    <img :src="product.image" class="room-img" />
    <h4
      @click="
        modalHandler = true;
        clickData = index;
      "
    >
      {{ product.title }}
    </h4>
    <p>{{ product.price }} 원</p>
  </div>

  <!-- <div>
    <img src="./assets/room0.jpg" class="room-img" />
    <h4 @click="modalHandler = true">{{ products[0].title }}</h4>
    <p>50 만원</p>
    <button v-on:click="count[0]++">허위매물신고</button>
    <span>신고수 : {{ count[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img" />
    <h4>{{ products[1] }}</h4>
    <p>60 만원</p>
    <button @click="count[1]++">허위매물신고</button>
    <span>신고수 : {{ count[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img" />
    <h4>{{ products[2] }}</h4>
    <p>70 만원</p>
    <button @click="count[2]++">허위매물신고</button>
    <span>신고수 : {{ count[2] }}</span>
  </div> -->
</template>

<script>
import data from "./assets/data";

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
  methods: {},
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
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
.room-img {
  width: 50%;
  margin-top: 40px;
}
</style>
