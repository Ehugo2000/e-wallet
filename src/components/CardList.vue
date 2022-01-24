<template>
  <div class="card-list">
    <Card v-if="!savedCardsArray" :card="card" class="single-card" />
    <Card
      :card="card"
      v-else
      v-for="(card, index) in savedCardsArray"
      :key="card.index"
      :class="{ active: index === 0 }"
    />
  </div>
</template>

<script>
import Card from "./Card.vue";
export default {
  name: "CardList",
  components: { Card },
  data() {
    return {
      savedCardsArray: [],
      card: {
        cardNumber: "",
        cardholderName: "",
        month: "",
        year: "",
        vendor: {},
        carId:'',
      },
    };
  },
  mounted() {
    console.log('mounteInCardList');
    this.savedCardsArray = JSON.parse(localStorage.getItem("savedCards"));
  },
  methods: {
  },
};
</script>

<style scoped>
.card-list {
  display: flex;
  flex-direction: column;
}


</style>