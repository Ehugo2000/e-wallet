<template>
  <div id="card-list">
    <Card />
  </div>
</template>

<script>
import Card from './Card.vue';
export default {
  name: 'CardList',
  components: { Card },
  data() {
    return {
      
    };
  },
};
</script>

<style>
#card-list {
  height: 337px;
  width: 382px;
  background-color: tomato;
}
</style>
