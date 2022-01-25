<template>
  <div>
    <div class="card" v-bind:style="cardTemplate" @click="$emit('activeCard')">
      <span class="upperpart">
        <div class="logos">
          <img :src="wifi" alt="wifi" id="wifiImg" />
          <img :src="chipImg" alt="chip" id="chipImg" />
        </div>
        <img :src="logo" alt="vendor-logo" />
      </span>
      <span class="middlepart"
        ><p id="cardnum">{{ cardNum }}</p></span
      >
      <span class="bottompart">
        <div class="name">
          <p class="cardText">CARDHOLDER NAME</p>
          <p class="cardinfo">{{ holderName }}</p>
        </div>
        <div class="valid-thru">
          <p class="cardText">VALID THRU</p>
          <p class="cardinfo">{{ `${validMonth}/${validYear}` }}</p>
        </div>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: ['card', 'vendors'],
  data() {
    return {
      wifiImg: require('../assets/wifi.svg'),
      chipImg: require('../assets/chip.svg'),
      whiteWifiImg: require('../assets/wifi_white.svg'),
      vendorLogo: require('../assets/bitcoin.svg'),
    };
  },
  computed: {
    cardTemplate() {
      console.log('cardTemplate');
      return {
        backgroundColor: this.card.vendor.backgroundColor,
        color: this.card.vendor.fontColor,
      };
    },
    wifi() {
      let inputData = '';
      if (this.card.vendor.name == 'Ninja Bank') {
        inputData = this.whiteWifiImg;
      } else {
        inputData = this.wifiImg;
      }
      return inputData;
    },
    logo() {
      let inputData = '';
      if (this.card.vendor.logo) {
        inputData = this.card.vendor.logo;
      } else {
        inputData = this.vendorLogo;
      }
      return inputData;
    },
    cardNum() {
      let inputData = '';
      if (this.card.cardNumber) {
        let sub1 = this.card.cardNumber.substring(0, 4);
        let sub2 = this.card.cardNumber.substring(4, 8);
        let sub3 = this.card.cardNumber.substring(8, 12);
        let sub4 = this.card.cardNumber.substring(12, 16);
        inputData = `${sub1} ${sub2} ${sub3} ${sub4}`;
        console.log('cardnumber1');
      } else {
        inputData = `XXXX XXXX XXXX XXXX`;
        console.log('cardnumber2');
      }
      return inputData;
    },
    holderName() {
      let inputData = '';
      if (this.card.name) {
        inputData = this.card.name;
      } else {
        inputData = `Firstname Lastname`;
      }
      return inputData;
    },
    validMonth() {
      let inputData = '';
      if (this.card.month) {
        inputData = this.card.month;
      } else {
        inputData = `XX`;
      }
      return inputData;
    },
    validYear() {
      let inputData = '';
      if (this.card.year) {
        inputData = this.card.year.substring(2, 4);
      } else {
        inputData = `XX`;
      }
      return inputData;
    },
  },
};
</script>

<style scoped>
.name {
  margin-left: 15px;
}
.valid-thru {
  margin-right: 15px;
}
.cardText {
  font-size: 10px;
  font-family: 'PT Mono', monospace;
  text-align: left;
}
.cardinfo {
  font-size: 15px;
  font-family: 'PT Mono', monospace;
  margin-top: 5px;
  letter-spacing: 0.1rem;
}
#cardnum {
  text-align: center;
  font-size: 23px;
  letter-spacing: 0.3rem;
  margin-top: 10px;
  font-family: 'PT Mono', monospace;
}
#wifiImg {
  max-width: 40px;
}
#chipImg {
  max-width: 40px;
}
.logos {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 20px;
  margin-left: 20px;
}
.upperpart {
  display: flex;
  justify-content: space-between;
}
.bottompart {
  display: flex;
  justify-content: space-between;
}
.card {
  background-color: #d0d0d0;
  border-radius: 5px;
  min-width: 350px;
  min-height: 200px;
  box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.32);
  margin-bottom: 40px;
}
</style>
