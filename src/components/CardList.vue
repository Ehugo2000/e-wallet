<template>
  <div class="card-list">
    <Card v-if="!savedCardsArray" :card="card" />
    <Card :card="card" v-for="card in savedCardsArray" :key="card" />
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardList',
  components: { Card },
  data() {
    return {
      savedCardsArray: [],
      card: {
        cardNumber: '',
        cardholderName: '',
        month: '',
        year: '',
        vendor: {},
        carId: '',
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
</style>
