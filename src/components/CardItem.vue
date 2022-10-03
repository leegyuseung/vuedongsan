<template>
  <div>
    <img :src="products.image" class="room-img" />
    <h4 @click="$emit('openModal', products.id)">
      {{ products.title }}
    </h4>
    <p>{{ products.price }} 원</p>
  </div>
  <!-- <div v-for="(product, index) in products" :key="index">
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
  </div> -->
</template>

<script>
export default {
  name: "CardItem",
  props: {
    products: Object,
  },
};
</script>

<style>
.room-img {
  width: 50%;
  margin-top: 40px;
}
</style>
