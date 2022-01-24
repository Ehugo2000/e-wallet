<template>
  <div class="card-list">
    <Card v-if="!savedCardsArray" :card="card" class="single-card" />
    <Card
      @wasClicked="changeActive(index)"
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
  mounted() {
    this.savedCardsArray = JSON.parse(localStorage.getItem("savedCards"));
  },
  data() {
    return {
      savedCardsArray: [],
      card: {
        cardNumber: "",
        cardholderName: "",
        month: "",
        year: "",
        vendor: {},
      },
    };
  },
  components: { Card },
  methods: {
    changeActive(index) {
      if (index > 0) {
        let newActive = this.savedCardsArray[index];
        this.savedCardsArray.splice(index, 1);
        this.savedCardsArray.unshift(newActive);
      }
    },
  },
};
</script>

<style scoped>
.card-list {
  display: flex;
  flex-direction: column;
}

.single-card:not(:first-of-type):hover {
  transform: translateY(-20%);
}
.single-card:not(:first-of-type) {
  position: relative;
  margin-bottom: -180px;
}


</style>