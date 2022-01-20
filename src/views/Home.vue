<template>
  <div id="home">
    <h4>ACTIVE CARD</h4>
    <Card />
    <button>ADD A NEW CARD</button>
  </div>
</template>

<script>
import Card from '../components/Card.vue';
export default {
  name: 'Home',
  components: { Card },
};
</script>

<style></style>
  