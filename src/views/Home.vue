<template>
  <div id="home">
    <h1>E-WALLET</h1>
    <h4>ACTIVE CARD</h4>
    <Card />
    <CardList />
    <button>ADD A NEW CARD</button>
  </div>
</template>

<script>
import Card from '../components/Card.vue';
import CardList from '../components/CardList.vue';

export default {
  name: 'Home',
  components: { Card, CardList },
};
</script>

<style>
#home {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
