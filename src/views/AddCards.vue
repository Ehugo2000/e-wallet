<template>
  <div id="add-cards">
    <h4>NEW CARD</h4>
    <Card />
    <RegisterCardForm/>
  </div>
</template>

<script>
import Card from '../components/Card.vue';
import RegisterCardForm from '../components/RegisterCardForm.vue';


export default {
  name: 'AddCards',
  components: { Card, RegisterCardForm },
};
</script>

<style></style>
