<template>
  <div id="app">
    <header>
      <nav>
        <a @click="currentView = 'home'">HOME</a>
        <a @click="currentView = 'addCards'">ADDCARDS</a>
      </nav>
    </header>
    <Home v-if="currentView == 'home'" />
    <AddCards v-if="currentView == 'addCards'" />
  </div>
</template>

<script>
import Home from './views/Home.vue';
import AddCards from './views/AddCards.vue';

export default {
  name: 'App',
  components: { Home, AddCards },
  data() {
    return {
      currentView: 'home',
    };
  },
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

nav {
  background-color: thistle;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;;
}

h1 {
  font-family: 'Source Sans Pro', sans-serif;
}

h4 {
  color:  #222222;
  opacity: 60%;
  
}

input {
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
