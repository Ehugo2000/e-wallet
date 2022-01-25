<template>
  <div class="card-list">
    <Card v-if="!savedCardsArray" :card="card" :class="{active: isActive}" @click="isActive = !isActive"/>
    <Card :card="card" v-for="card in savedCardsArray" :key="card.cardNumber" />
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardList',
  components: { Card },
  data() {
    return {
      isActive: "false",
      savedCardsArray: [],
      card: {
        cardNumber: '',
        cardholderName: '',
        month: '',
        year: '',
        vendor: {},
        cardId: '',
      },
    };
  },
  mounted() {
    console.log('mounteInCardList');
    this.savedCardsArray = JSON.parse(localStorage.getItem('savedCards'));
  },
  methods: {},
};
</script>

<style scoped>
.card-list {
  display: flex;
  flex-direction: column;
}

.active {
  background-color: green;
}
</style>
