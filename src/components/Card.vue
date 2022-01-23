<template>
  <div class="card" @submit="$emit('submit', savedCards)">
    <div class="card" v-bind:style="cardStyle">
      <span class="upperpart">
        <div class="logos">
          <img :src="wifi" alt="Wifi-logo" id="wifiImg" />
          <img :src="chipImg" alt="Chip-logo" id="chipImg" />
        </div>
        <img :src="logo" alt="Vendor-logo" />
      </span>
      <span class="middlepart"
        ><p id="cardnum">{{ cardNum }}</p></span
      >
      <span class="bottompart">
        <div class="name">
          <p class="cardheader">CARDHOLDER NAME</p>
          <p class="cardinfo">{{ holderName }}</p>
        </div>
        <div class="valid-thru">
          <p class="cardheader">VALID THRU</p>
          <p class="cardinfo">{{ `${validMonth}/${validYear}` }}</p>
        </div>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ['user', 'vendors'],
  data() {
    return {
      wifiImg: require('../assets/wifi.svg'),
      chipImg: require('../assets/chip.svg'),
      whiteWifiImg: require('../assets/wifi_white.svg'),
      vendorLogo: require('../assets/bitcoin.svg'),
    };
  },

  computed: {
    wifi() {
      let span = '';
      if (this.user.vendor.name == 'Ninja Bank') {
        span = this.whiteWifiImg;
      } else {
        span = this.wifiImg;
      }
      return span;
    },
    cardStyle() {
      return {
        backgroundColor: this.user.vendor.backgroundColor,
        color: this.user.vendor.fontColor,
      };
    },
    logo() {
      let span = '';
      if (this.user.vendor.logo) {
        span = this.user.vendor.logo;
      } else {
        span = this.vendorLogo;
      }
      return span;
    },
    cardNum() {
      let span = '';
      if (this.user.cardNumber) {
        let sub1 = this.user.cardNumber.substring(0, 4);
        let sub2 = this.user.cardNumber.substring(4, 8);
        let sub3 = this.user.cardNumber.substring(8, 12);
        let sub4 = this.user.cardNumber.substring(12, 16);
        span = `${sub1} ${sub2} ${sub3} ${sub4}`;
      } else {
        span = `XXXX XXXX XXXX XXXX`;
      }
      return span;
    },
    holderName() {
      let span = '';
      if (this.user.name) {
        span = this.user.name;
      } else {
        span = `Firstname Lastname`;
      }
      return span;
    },
    validMonth() {
      let span = '';
      if (this.user.month) {
        span = this.user.month;
      } else {
        span = `XX`;
      }
      return span;
    },
    validYear() {
      let span = '';
      if (this.user.year) {
        span = this.user.year.substring(2, 4);
      } else {
        span = `XX`;
      }
      return span;
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
.cardheader {
  font-size: 10px;
  font-family: 'PT Mono', monospace;
  text-align: left;
}
.cardinfo {
  font-size: 15px;
  font-family: 'PT Mono', monospace;
  margin-top: 5px;
}
#cardnum {
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
  box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.81);
  margin-bottom: 40px;
}
</style>
