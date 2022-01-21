<template>
  <div id="home">
    <h1>E-WALLET</h1>
    <h4>ACTIVE CARD</h4>
    <div id="card">
      <div class="card-logos">
        <div class="card-logos-left">
          <img src="../assets/wifi.svg" alt="wifi" />
          <img src="../assets/chip.svg" alt="chip" />
        </div>
        <img src="../assets/bitcoin.svg" alt="bitcoin" />
      </div>
      <h2>XXXX XXXX XXXX XXXX</h2>
      <div class="card-info">
        <div>
          <p>CARDHOLDER NAME</p>
          <h3>CARDHOLODER NAME</h3>
        </div>
        <div>
          <p>VALID THRU</p>
          <h3>10/20</h3>
        </div>
      </div>
    </div>

    <div class="card-list">future component</div>
    <button @click="$emit('viewChange')">ADD A NEW CARD</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {},
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
</style>
