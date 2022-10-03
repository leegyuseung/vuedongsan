<template>
  <!-- modal창 -->
  <div class="black-bg" v-if="modalHandler === true">
    <div class="white-bg">
      <h4>{{ products[clickData].title }}</h4>
      <img :src="products[clickData].image" />
      <p>{{ products[clickData].content }}</p>
      <p>{{ products[clickData].price }} 원</p>
      <DiscountBanner />
      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<script>
import DiscountBanner from "./DiscountBanner.vue";
export default {
  name: "ModalContent",
  props: {
    products: Array,
    modalHandler: Boolean,
    clickData: Number,
  },
  methods: {
    close() {
      this.$emit("closeModal");
    },
  },
  components: { DiscountBanner },
};
</script>

<style>
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
</style>
