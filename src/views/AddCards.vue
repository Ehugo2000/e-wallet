<template>
  <div id="add-cards">
    <h1>ADD A NEW BANK CARD</h1>
    <h4>NEW CARD</h4>
    <Card />
    <RegisterCardForm />
  </div>
</template>

<script>
import Card from '../components/Card.vue';
import RegisterCardForm from '../components/RegisterCardForm.vue';

export default {
  name: 'AddCards',
  components: { Card, RegisterCardForm },
  props: ['']
};
</script>

<style>
#add-cards {
  margin: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
