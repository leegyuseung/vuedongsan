<template>
  <!-- 홍보 배너 -->
  <div class="discount">
    <h4>지금 결제하면 {{ percent }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: "DiscountBanner",
  data() {
    return {
      percent: 30,
    };
  },
  mounted() {
    setInterval(() => {
      this.percent--;
    }, 1000);
  },
};
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
