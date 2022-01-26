<template>
  <div>
    <Card v-if="savedCardsArray.length <= 0" :card="card" :savedCardsArray='savedCardsArray'/>
    <div class="card-list">
    <Card
      :card="card"
      :savedCardsArray='savedCardsArray'
      v-for="(card, ArrayIndex) in savedCardsArray"
      :key="card.index"
      @activeCard="activeCard(ArrayIndex)"
    />

    </div>
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardList',
  components: { Card },
  props: ['savedCardsArray'],
  data() {
    return {
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
  methods: {
    activeCard(ArrayIndex) {
 if (ArrayIndex != 0) {
        let setActiveCard = this.savedCardsArray[ArrayIndex];
        this.savedCardsArray.splice(ArrayIndex, 1);
        this.savedCardsArray.unshift(setActiveCard);
      }
    },
  },
};
</script>

<style scoped>
.card-list {
  height: 600px;
  display: grid;
  grid-auto-rows: 240px 80px 80px 80px;
}



</style>
