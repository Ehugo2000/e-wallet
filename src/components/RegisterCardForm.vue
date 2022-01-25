<template>
  <div id="register-card-form">
    <Card :card="card" :vendors="vendors"/>
    <form class="form" @submit.prevent="submit">
      <label for="card-number">CARD NUMBER</label>
      <input
        type="number"
        name="card-number"
        placeholder="XXXX XXXX XXXX XXXX"
        class="card-number"
        v-model="card.cardNumber"
      />
      <label for="cardholder-name">CARDHOLDER NAME</label>
      <input
        type="text"
        name="cardholder-name"
        placeholder="FIRSTNAME LASTNAME"
        class="cardholder-name"
        v-model="card.name"
      />
      <div class="date">
        <div class="valid">
          <label for="month">MONTH</label>
          <select name="month" v-model="card.month">
            <option v-for="month in months" :key="month" value:value="month" name="month">
              {{ month }}
            </option>
          </select>
        </div>

        <div class="valid">
          <label for="year">YEAR</label>
          <select name="year" v-model="card.year">
            <option v-for="year in years" :key="year" value:value="year" name="year">
              {{ year }}
            </option>
          </select>
        </div>
      </div>

      <label for="vendor">VENDOR</label>
      <select class="vendor" name="vendor" v-model="card.vendor">
        <option
          v-for="vendor in vendors"
          :key="vendor.name"
          :value="vendor"
          name="vendor"
        >
          {{ vendor.name }}
        </option>
      </select>
      <button class="add-new-card-btn" @submit="submit">ADD CARD</button>
    </form>
  </div>
</template>

<script>
function generateId() {
  console.log('generatID');
  return Math.floor(Math.random() * 10000);
}
import Card from '../components/Card.vue';

export default {
  name: 'RegisterCardForm',
  components: { Card },
  props: [''],
  data() {
    return {
      savedCardsArray: [],
      card: {
        cardNumber: '',
        name: '',
        year: '',
        month: '',
        vendor: {},
        cardId: generateId(),
      },
      months: [
        '01',
        '02',
        '03',
        '04',
        '05',
        '06',
        '07',
        '08',
        '09',
        '10',
        '11',
        '12',
      ],
      years: ['2022', '2023', '2024', '2025', '2026'],
      vendors: [
        {
          name: 'Bitcoin Inc',
          backgroundColor: '#FFAE34',
          fontColor: 'black',
          logo: require('../assets/bitcoin.svg'),
        },
        {
          name: 'Ninja Bank',
          backgroundColor: '#222222',
          fontColor: 'white',
          logo: require('../assets/ninja.svg'),
        },
        {
          name: 'Block Chain Inc',
          backgroundColor: '#8B58F9',
          fontColor: 'white',
          logo: require('../assets/blockchain.svg'),
        },
        {
          name: 'Evil Corp',
          backgroundColor: '#F33355',
          fontColor: 'white',
          logo: require('../assets/evil.svg'),
        },
      ],
    };
  },
  methods: {
    submit() {

      this.$emit('clickToChangeView');
      console.log(localStorage);
    },
  },
   beforeDestroy() {
    if (localStorage.getItem("savedCards") != undefined) {
      this.savedCardsArray = JSON.parse(localStorage.getItem("savedCards"));
      console.log('beforeDestroyIF');
    }
      this.savedCardsArray.push(this.card);
      localStorage.setItem("savedCards", JSON.stringify(this.savedCardsArray));
      console.log('beforeDestroysetItem');
    
  },
};
</script>

<style>
.form {
  display: flex;
  flex-direction: column;
}

input,
select {
  font-size: 18px;
  border-radius: 8px;
  min-height: 56px;
}

label {
  margin: 5px;
  margin-top: 10px;
}

.card-number {
  height: 56px;
  width: 382px;
}

.cardholder-name {
  height: 56px;
  width: 382px;
}

.date {
  display: flex;
  justify-content: space-between;
  margin-bottom: 35px;
}

.valid {
  height: 56px;
  width: 175px;
  display: flex;
  flex-direction: column;
}

.vendor {
  height: 56px;
  width: 382px;
}

.add-new-card-btn {
  border: none;
  background-color: black;
  color: white;
}
</style>
