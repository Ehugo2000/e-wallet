<template>
  <div id="register-card-form">
    <form @submit.prevent="submit">
      <input
        type="number"
        name="card-number"
        placeholder="XXXX XXXX XXXX XXXX"
        class="card-number"
        v-model="user.cardnumber"
      />
      <input
        type="text"
        placeholder="FIRSTNAME LASTNAME"
        class="cardholder-name"
        v-model="user.name"
      />
      <input
        type="date"
        placeholder="XX/XX"
        class="valid"
        v-model="user.valid"
      />
      <input type="number" placeholder="XXX" class="ccv" v-model="user.ccv" />
      <input
        type="text"
        placeholder="CHOOSE A VENDOR"
        class="vendor"
        v-model="user.vendor"
      />
      <button @click="$emit('viewChange')">ADD CARD</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'RegisterCardForm',
  props: [''],
  data() {
    return {
      user: {
        cardnumber: '',
        name: '',
        valid: '',
        ccv: '',
        vendor: '',
      },
    };
  },
  methods: {
    submit() {
      this.$emit('addInfoToCard', {...this.user})
    },
  },
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
