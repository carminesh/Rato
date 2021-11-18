<template>

      <div class="exchange-container">
        <form class="form-container" @click.prevent>
          <div class="amount-container">
            <h2>Amount</h2>
            <input type="number" placeholder="1.00" required>
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
            <button class="swap-btn"><i class="fas fa-exchange-alt"></i></button>
          </div>
           <button class="btn-convert">Convert</button>
        </form>

        <div class="result-container">
          <h2>Converted value</h2>
          <div class="result">
            <div class="text">
              <h3>
                <span id="from-value">USD</span>
                <span id="equal">=</span>
                <span id="to-value">EUR</span>
              </h3>
            </div>
          </div>
        </div>
      </div>
  
</template>

<script>

export default {
  name: 'FormContainer',
  
  data() {
    return {
      fromCurrency : 'USD',
      toCurrency : 'EUR'
    }
  }

}




</script>

<style scoped>

 .exchange-container {
    margin-top: 20px;
    background-color: #ffffff;
    width: 100%;
    height: 70%;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .form-container {
    width: 90%;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
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
    transition: all 0.3s ease-in-out;
  }

  .swap-btn:hover {
    border: solid 3px #2F2E32;
  }
  .swap-btn:hover i{
    color: #2F2E32;
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
    border: solid 3px #3872FF;
    border-radius: 5px;
    height: 48px;
    padding: 0rem 1.5rem;
    cursor: pointer;
    transition: all 0.3s ease-in-out;
  }

  .btn-convert:hover {
    background: none;
    border: solid 3px #3872FF; 
    color: #3872FF;
  }

  .result-container {
    align-self: flex-start;
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 81%;
    margin: 20px auto;
  }

  .result {
    margin-top: 5px;
    width: 250px;
    padding: 0.7rem 4.4rem;
    border: solid 2px #2F2E32;
    border-radius: 5px;
  }

  #equal {
    margin: 0 10px;
  }
  
</style>
