<template>
  <!-- modal창 -->
  <div class="black-bg" v-if="modalHandler === true">
    <div class="white-bg">
      <h4>{{ products[clickData].title }}</h4>
      <img :src="products[clickData].image" />
      <p>{{ products[clickData].content }}</p>
      <!-- <input @input="month = $event.target.value" /> -->
      <!-- <textarea v-model='month' /> -->
      <input v-model.number="month" />
      <p>{{ month }}개월 선택함 : {{ products[clickData].price * month }} 원</p>
      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalContent",
  props: {
    products: Array,
    modalHandler: Boolean,
    clickData: Number,
  },
  data() {
    return {
      month: 1,
    };
  },
  methods: {
    close() {
      this.$emit("closeModal");
    },
  },
  watch: {
    month(a) {
      if (a >= 13) {
        alert("13이상 입력하지 마셈");
      }
      if (typeof a !== "number") {
        alert("숫자를 입력하세요");
        a = 1;
      }
    },
  },
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
