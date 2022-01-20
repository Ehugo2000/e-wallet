<template>
  <div id="add-cards">
    <h4>NEW CARD</h4>
    <Card />
    <button>ADD CARD</button>
  </div>
</template>

<script>
import Card from '../components/Card.vue';

export default {
  name: 'AddCards',
  components: { Card },
};
</script>

<style></style>
