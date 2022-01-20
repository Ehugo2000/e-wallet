<template>
  <div id="app">
  <Home/>
  <AddCards/>
  </div>
</template>

<script>
import Home from "./views/Home.vue";
import AddCards from "./views/AddCards.vue";

export default {
  name: "App",
  components: { Home, AddCards }

}
</script>

<style>
  #app{
    margin: auto;
    height: 896px;
    width: 414px;
    background-color: peachpuff;
  }

</style>