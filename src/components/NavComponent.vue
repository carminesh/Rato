<template>
  <div class="nav-container">
    <a href="#"><img id="logo" src="../assets/logo.svg" alt="logo"></a>
    <div class="base-currency">
      <h3>Base Currency</h3>

      <select v-model="defaultValue" name="base-currency-selector" id="currency-selector" @input="$emit('base-currency-input', $event.target.value)" :value="value">
        <option v-for="(option, index) in options" :key="index" :value="option">{{option}}</option>
      </select>


    </div>
  </div>
  
</template>

<script>

export default {
  name: 'NavComponent',

  data() {
    return {
      defaultValue : 'EUR',
      options: ['EUR', 'USD']
    }
  }

}
</script>

<style scoped>

  .nav-container {
    background-color: #2F2E32;
    min-height: 5%;
    width: 80%;
    margin: auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2rem 0rem;
    color: white;

  }

  #logo {
    width: 65px;
    object-fit: cover;
  }

  .base-currency {
    margin-right: 4vw;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  #currency-selector {
    background-color: #ffff;
    margin-left: 20px;
    width: 90px;
    height: 45px;
    border-radius: 5px;
    color: #2F2E32;
    font-size: 1.2rem;
    font-weight: 500;
  }


</style>
