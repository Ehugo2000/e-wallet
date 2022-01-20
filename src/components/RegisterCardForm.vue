<template>
  <div id="register-card-form">
    <form @submit.prevent>
      <input
        type="number"
        name="card-number"
        placeholder="XXXX XXXX XXXX XXXX"
        class="card-number"
      />
      <input
        type="text"
        placeholder="FIRSTNAME LASTNAME"
        class="cardholder-name"
      />
      <input type="number" placeholder="XX/XX" class="valid" />
      <input type="number" placeholder="XXX" class="ccv" />
      <input type="text" placeholder="CHOOSE A VENDOR" class="vendor" />
      <button class="add-card-btn">ADD CARD</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'RegisterCardForm',
};
</script>

<style>
input {
  font-size: 18px;
  border-radius: 8px;
}
.card-number {
  height: 56px;
  width: 382px;
}

.cardholder-name {
  height: 56px;
  width: 382px;
}

.valid {
  height: 56px;
  width: 175px;
}

.ccv {
  height: 56px;
  width: 175px;
}
.vendor {
  height: 56px;
  width: 382px;
}

.add-card-btn {
  border: none;
  background-color: black;
  color: white;
}
</style>
