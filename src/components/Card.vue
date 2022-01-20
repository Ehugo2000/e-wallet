<template>
  <div id="card">
    <div class="card-logos">
      <div class="card-logos-left">
    <img src="../assets/wifi.svg" alt="wifi">
    <img src="../assets/chip.svg" alt="chip">
      </div>
    <img src="../assets/bitcoin.svg" alt="bitcoin">
    </div>
    <h2>**inputdata cardnumber</h2>
    <div class="card-info">
    <p>CARDHOLDER NAME</p>
    <p>VALID THRU</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
};
</script>

<style>
#card {
  height: 241px;
  width: 382px;
  background-color: #d0d0d0;
  border-radius: 8px;
  box-shadow: 8px 9px 32px 1px rgba(0,0,0,0.13);
  display: flex;
  flex-direction: column;
  
}

.card-logos{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}

.card-logos-left{
  display: flex;
  flex-direction: column;
  padding-top: 10px;
  padding-left: 10px;
}

.card-info{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
</style>
