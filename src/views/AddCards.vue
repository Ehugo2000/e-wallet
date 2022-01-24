<template>
  <div id="add-cards">
    <h1>ADD A NEW BANK CARD</h1>
    <h4>NEW CARD</h4>
    <RegisterCardForm @clickToChangeView="$emit('clickToChangeView')" />
  </div>
</template>

<script>
import RegisterCardForm from '../components/RegisterCardForm.vue';

export default {
  name: 'AddCards',
  components: { RegisterCardForm },
  props: ['sendFormDataTo'],
  data(){return {
    sendFormDataToCard: {},

  }},
  methods: {
    
  }
};
</script>

<style>
#add-cards {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
