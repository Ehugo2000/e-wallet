<template>
  <div id="home">
    <h1>E-WALLET</h1>
    <h4>ACTIVE CARD</h4>
    <div id="card">
          ACTIVE CARD HERE
    </div>

    <div class="card-list">
      <!-- <CardList/> -->
    </div>
    <button @click="$emit('viewChange')" class="add-card-btn">ADD A NEW CARD</button>
  </div>
</template>

<script>
// import CardList from "../components/CardList.vue";
export default {
  name: 'Home',
  // components: { CardList },
  data() {
    return {
      currentView: 'addCards',
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
  height: 337px;
  width: 382px;
  background-color: tomato;
}

.add-card-btn{
 border: none;
  background-color: white;
  color: black;
}
</style>
