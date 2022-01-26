<template>
  <div class="card-list">
    <Card v-if="!savedCardsArray" :card="card"/>
    <Card :card="card" v-for="(card, index) in savedCardsArray" :key="card.index"
    @activeCard="log(index)"
    />
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardList',
  components: { Card },
  data() {
    return {
      // isActive: "false", :class="{active: isActive}" @click="isActive = !isActive"
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
  created() {
    console.log('mounteInCardList');
    this.savedCardsArray = JSON.parse(localStorage.getItem('savedCards'));
  },
  methods: {
    log(index){
    console.log(JSON.stringify(this.savedCardsArray[index]) + " " + JSON.parse(index));
    }
  },
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