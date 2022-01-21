<template>
  <div id="add-cards">
    <h1>ADD A NEW BANK CARD</h1>
    <h4>NEW CARD</h4>
    <Card :sendFormDataToCard="sendFormDataToCard"/>
    <RegisterCardForm @viewChange="$emit('viewChange')"/>
  </div>
</template>

<script>
import Card from '../components/Card.vue';
import RegisterCardForm from '../components/RegisterCardForm.vue';

export default {
  name: 'AddCards',
  components: { Card, RegisterCardForm },
  props: ['sendFormDataTo'],
  data(){return {
    sendFormDataToCard: {},

  }},
  methods: {
    register(formData){
      this.sendFormDataToCard = formData
      console.log(this.sendFormDataToCard);
    },
     clickAdd() {
      return this.$emit("viewChange");
    },
  }
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
