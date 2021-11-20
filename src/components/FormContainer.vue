<template>

      <div class="exchange-container">

        <button class="refresh-btn" @click="updateCurrency"><i class="fas fa-sync-alt"></i></button>
        
        <form class="form-container">
          <div class="amount-container">
            <h2>Amount</h2>
            <input type="number" placeholder="1.00" v-model="amount" required>
          </div>
          <div class="fromCurrency-container">
            <h2>From Currency</h2>
            <select name="from-currency" id="from-currency" v-model="fromCurrency">
              <option value="AED">AED</option>
              <option value="ARS">ARS</option>
              <option value="AUD">AUD</option>
              <option value="BGN">BGN</option>
              <option value="BRL">BRL</option>
              <option value="BSD">BSD</option>
              <option value="CAD">CAD</option>
              <option value="CHF">CHF</option>
              <option value="CLP">CLP</option>
              <option value="CNY">CNY</option>
              <option value="COP">COP</option>
              <option value="CZK">CZK</option>
              <option value="DKK">DKK</option>
              <option value="DOP">DOP</option>
              <option value="EGP">EGP</option>
              <option value="EUR">EUR</option>
              <option value="FJD">FJD</option>
              <option value="GBP">GBP</option>
              <option value="GTQ">GTQ</option>
              <option value="HKD">HKD</option>
              <option value="HRK">HRK</option>
              <option value="HUF">HUF</option>
              <option value="IDR">IDR</option>
              <option value="ILS">ILS</option>
              <option value="INR">INR</option>
              <option value="ISK">ISK</option>
              <option value="JPY">JPY</option>
              <option value="KRW">KRW</option>
              <option value="KZT">KZT</option>
              <option value="MXN">MXN</option>
              <option value="MYR">MYR</option>
              <option value="NOK">NOK</option>
              <option value="NZD">NZD</option>
              <option value="PAB">PAB</option>
              <option value="PEN">PEN</option>
              <option value="PHP">PHP</option>
              <option value="PKR">PKR</option>
              <option value="PLN">PLN</option>
              <option value="PYG">PYG</option>
              <option value="RON">RON</option>
              <option value="RUB">RUB</option>
              <option value="SAR">SAR</option>
              <option value="SEK">SEK</option>
              <option value="SGD">SGD</option>
              <option value="THB">THB</option>
              <option value="TRY">TRY</option>
              <option value="TWD">TWD</option>
              <option value="UAH">UAH</option>
              <option value="USD">USD</option>
              <option value="UYU">UYU</option>
              <option value="VND">VND</option>
              <option value="ZAR">ZAR</option>
            </select>
            
          </div>
           <div class="toCurrency-container">
            <h2>To Currency</h2>
            <select name="toCurrency" id="toCurrency" v-model="toCurrency">
              <option value="AED">AED</option>
              <option value="ARS">ARS</option>
              <option value="AUD">AUD</option>
              <option value="BGN">BGN</option>
              <option value="BRL">BRL</option>
              <option value="BSD">BSD</option>
              <option value="CAD">CAD</option>
              <option value="CHF">CHF</option>
              <option value="CLP">CLP</option>
              <option value="CNY">CNY</option>
              <option value="COP">COP</option>
              <option value="CZK">CZK</option>
              <option value="DKK">DKK</option>
              <option value="DOP">DOP</option>
              <option value="EGP">EGP</option>
              <option value="EUR">EUR</option>
              <option value="FJD">FJD</option>
              <option value="GBP">GBP</option>
              <option value="GTQ">GTQ</option>
              <option value="HKD">HKD</option>
              <option value="HRK">HRK</option>
              <option value="HUF">HUF</option>
              <option value="IDR">IDR</option>
              <option value="ILS">ILS</option>
              <option value="INR">INR</option>
              <option value="ISK">ISK</option>
              <option value="JPY">JPY</option>
              <option value="KRW">KRW</option>
              <option value="KZT">KZT</option>
              <option value="MXN">MXN</option>
              <option value="MYR">MYR</option>
              <option value="NOK">NOK</option>
              <option value="NZD">NZD</option>
              <option value="PAB">PAB</option>
              <option value="PEN">PEN</option>
              <option value="PHP">PHP</option>
              <option value="PKR">PKR</option>
              <option value="PLN">PLN</option>
              <option value="PYG">PYG</option>
              <option value="RON">RON</option>
              <option value="RUB">RUB</option>
              <option value="SAR">SAR</option>
              <option value="SEK">SEK</option>
              <option value="SGD">SGD</option>
              <option value="THB">THB</option>
              <option value="TRY">TRY</option>
              <option value="TWD">TWD</option>
              <option value="UAH">UAH</option>
              <option value="USD">USD</option>
              <option value="UYU">UYU</option>
              <option value="VND">VND</option>
              <option value="ZAR">ZAR</option>
            </select>
          </div>
           <div class="swap-container">
            <h2 id="swap-text">Swap</h2>
            <button class="swap-btn" @click.prevent="swapCurrency"><i class="fas fa-exchange-alt"></i></button>
          </div>
           <button type="submit" class="btn-convert" @click.prevent="convertCurrency">Convert</button>
        </form>

        <div class="result-container">
          <div class="result">
              <h2>Converted value</h2>
                <div class="result-text">
                  <span id="from-value">{{amount}} {{fromCurrency}}</span>
                  <span id="equal">=</span>
                  <span id="to-value">{{result}} {{toCurrency}}</span>
                </div>
          </div>
        </div>

      </div>
  
</template>

<script>

import axios from "axios"
import gsap from 'gsap'

export default {
  name: 'FormContainer',

  props: {
     currency: {
          type: String,
          required: true
      }
  },
  
  data() {
    return {
      amount: '1',
      fromCurrency : 'EUR',
      toCurrency : 'USD',
      result: '1',
      date: ''
    }
  },
  methods: {
    
    //Update all currency input based on the current chosen currency
    updateCurrency() {
      this.fromCurrency = this.currency;
      if(this.fromCurrency == 'EUR') { 
        this.toCurrency = 'USD';
      } else {
        this.toCurrency = 'EUR'
      }
    },

    //Fetch data from the API
    async convertCurrency() {

      try {
        const res = await axios.get(`https://api.exchangerate.host/convert?from=${this.fromCurrency}&to=${this.toCurrency}&amount=${this.amount}`);
        this.date = res.data.date;
        this.result = parseInt(res.data.result).toFixed(2);
      }catch(e) {
        console.error(e);
      }

    },

    //Function that enable the currency swap
    swapCurrency() {
      const currency = this.fromCurrency;
      this.fromCurrency = this.toCurrency;
      this.toCurrency = currency;
    }

  },

  mounted: function() {
    gsap.from('.refresh-btn', {y: -200, duration: 1, ease: 'Power1.easeOut'});
  }

}

</script>

<style scoped>


 .exchange-container {
    margin-top: 20px;
    background-color: #ffffff;
    width: 100%;
    height: 65%;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
  }

  .form-container {
    width: 80%;
    display: flex;
    justify-content: space-between;
  }

  .amount-container input {
    margin-top: 5px;
    padding: 0.7rem;
    border: solid 2px #2F2E32;
    border-radius: 5px;
  }

  .fromCurrency-container select {
    margin-top: 5px;
    padding: 0.7rem 4.4rem;
    border: solid 2px #2F2E32;
    border-radius: 5px;
  }

  .toCurrency-container select {
    margin-top: 5px;
    padding: 0.7rem 3.5rem;
    border: solid 2px #2F2E32;
    border-radius: 5px;
  }

  #swap-text {
    color:#3872FF;
  } 

  .swap-btn {
    margin-top: 5px;
    background: none;
    padding: 0.4rem 1rem;
    border: solid 3px #3872FF;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
  }

  .swap-btn:hover {
    border: solid 3px #244cb3;
  }
  .swap-btn:hover i{
    color: #244cb3;
  }

  i {
    font-size: 1.5rem;
    color: #3872FF;
    pointer-events: none;
  }

  .btn-convert {
    align-self: flex-end;
    color: white;
    font-weight: bold;
    font-size: 1.1rem;
    background-color: #3872FF;
    border: none;
    border-radius: 5px;
    height: 48px;
    padding: 0rem 1.5rem;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
  }

  .btn-convert:hover {
    background: #244cb3;
    color: white;
  }

  .result-container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 80%;
  }

  .result-text {
    font-size: 2rem;
    font-weight: bold;
    color:#3872FF;
  }

  #equal {
    margin: 0 10px;
  }

  .refresh-btn i {
    font-size: 1.5rem;
    pointer-events: none;
    color: #3872FF;
  }

  .refresh-btn {
  
    padding: 0.7rem;
    border: none;
    background: none;
    cursor: pointer;
    position: absolute;
    right: 9.5vw;
    top: 46px;
  }

  /* MEDIA QUERIES */

  /*Mobile devices*/
  @media screen and (max-width: 480px) {

    .exchange-container {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
    }

    .form-container {
      margin-top: 20px;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .amount-container input {
      margin-top: 5px;
      width: 100%;
    }

    .fromCurrency-container select {
      width: 100%;
    }

    .toCurrency-container select {
      width: 100%;
    }

    .swap-btn {
      width: 100%;
      padding: 0.7rem 0;
    }

    .btn-convert {
      margin-top: 10px;
      font-size: 1.5rem;
      width: 100%;
    }

    .btn-convert:hover {
      background: #244cb3;
      color: white;
    }

    .result-container {
      font-size: 1.5rem;
      margin: 20px 0;
    }

    .result-text {
      font-size: 2.5rem;
    }

    .refresh-btn i {
      font-size: 2rem;
      pointer-events: none;
      color: #3872FF;
    }

    .refresh-btn {
      overflow: auto !important;
      position: absolute;
      right: 6vw;
      top: 6.5vh;
    }
    

  }

  /*iPads, Tablets devices*/
  @media screen and (min-width: 481px) and (max-width: 768px) {

    .exchange-container {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
    }

    .form-container {
      margin-top: 20px;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .amount-container input {
      margin-top: 5px;
      width: 100%;
    }

    .fromCurrency-container, .toCurrency-container, .swap-container {
      margin-top: 10px;
    } 

    .fromCurrency-container select {
      width: 100%;
    }

    .toCurrency-container select {
      width: 100%;
    }

    .swap-btn {
      width: 100%;
      padding: 0.7rem 0;
    }

    .btn-convert {
      margin-top: 20px;
      font-size: 1.5rem;
      width: 100%;
    }

    .result-container {
      font-size: 1.5rem;
      margin: 20px 0;
    }

    .result-text {
      font-size: 2.5rem;
    }

    .refresh-btn i {
      font-size: 2rem;
      pointer-events: none;
      color: #3872FF;
    }

    .refresh-btn {
      overflow: auto !important;
      position: absolute;
      right: 6vw;
      top: 4vh;
    }

  }

   /*Small screens, laptops*/
  @media screen and (min-width: 769px) and (max-width: 1324px) {
    
    .exchange-container {
      width: 100%;
      height: 100%;
      display: flex;
      flex-direction: column;
    }

    .form-container {
      margin-top: 20px;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .amount-container input {
      margin-top: 5px;
      width: 100%;
    }

    .fromCurrency-container, .toCurrency-container, .swap-container {
      margin-top: 10px;
    } 

    .fromCurrency-container select {
      width: 100%;
    }

    .toCurrency-container select {
      width: 100%;
    }

    .swap-btn {
      width: 100%;
      padding: 0.7rem 0;
    }

    .btn-convert {
      margin-top: 20px;
      font-size: 1.5rem;
      width: 100%;
    }

    .result-container {
      font-size: 1.5rem;
      margin: 20px 0;
    }

    .result-text {
      font-size: 2.5rem;
    }

    .refresh-btn i {
      font-size: 2rem;
      pointer-events: none;
      color: #3872FF;
    }

    .refresh-btn {
      overflow: auto !important;
      position: absolute;
      right: 6vw;
      top: 3.2vh;
    }
  
  }

  /*Large screen*/
  @media screen and (min-width: 1320px) and (max-width: 1400px) {

    .form-container {
      width: 90%;
    }

    .result-container {
      width: 90%;
    }

    .btn-convert {
      height: 52%;
    }
    
    .refresh-btn {
      overflow: auto !important;
      position: absolute;
      right: 9vw;
      top: 4.2vh;
    }
  }
  
</style>
