<template>
  <div id="home">
    <h1>E-WALLET</h1>
    <h4>ACTIVE CARD</h4>
    <div class="card-list">
      <CardList/>
    </div>
    <button @click="$emit('clickToChangeView')" class="add-card-btn">ADD A NEW CARD</button>
  </div>
</template>

<script>
import CardList from "../components/CardList.vue";
export default {
  name: 'Home',
  components: { CardList },
  data() {
    return {
    };
  },
};
</script>

<style>
#home {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.card-list {
  height: 660px;
  width: 386px;
}

.add-card-btn{
 border: none;
  background-color: white;
  color: black;
}
</style>
