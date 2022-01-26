<template>
  <div id="app">
    <Home
      v-if="currentView == 'home'"
      @clickToChangeView="changeView"
      :savedCardsArray="savedCardsArray"
    />
    <AddCards v-else @clickToChangeView="changeView" @saveCard="saveCard" />
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
      savedCardsArray: [],
      currentView: 'home',
    };
  },
  mounted() {
    if (localStorage.getItem('savedCards') != undefined) {
      this.savedCardsArray = JSON.parse(localStorage.getItem('savedCards'));
    }
  },
  methods: {
    saveCard(card) {
      this.savedCardsArray.push(card);
      localStorage.setItem('savedCards', JSON.stringify(this.savedCardsArray));
    },
    changeView() {
      this.currentView == 'home'
        ? (this.currentView = 'addCards')
        : (this.currentView = 'home');
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=PT+Mono&display=swap');

#app {
  display: flex;
  justify-content: center;
  margin: auto;
  height: 896px;
  width: 414px;
  background-color: rgb(226, 226, 226);
  text-transform: uppercase;
  border-radius: 6px;
}

h1 {
  font-family: 'Source Sans Pro', sans-serif;
}

h4 {
  color: #222222;
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
