<template>
  <div id="app">
    <h1>E-WALLET</h1>
    <h1>ADD A NEW BANK CARD</h1>
    <Home />
    <AddCards />
  </div>
</template>

<script>
import Home from './views/Home.vue';
import AddCards from './views/AddCards.vue';

export default {
  name: 'App',
  components: { Home, AddCards },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=PT+Mono&display=swap');

#app {
  margin: auto;
  height: 896px;
  width: 414px;
  background-color: peachpuff;
}

h1 {
  font-family: 'Source Sans Pro', sans-serif;
}

p {
  font-family: 'PT Mono', monospace;
}

button {
  font-family: 'PT Mono', monospace;
  font-size: 22px;
  width: 382px;
  height: 72px;
  border-radius: 8px;
}
</style>
