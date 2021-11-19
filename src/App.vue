<template>

  <NavComponent @base-currency-input="baseCurrency"></NavComponent>
  <MainComponent :currency="currency"></MainComponent>
  <FooterComponent></FooterComponent>

</template>

<script>
import NavComponent from './components/NavComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    NavComponent,
    MainComponent,
    FooterComponent
  },

  data() {
    return {
      currency: ''
    }
  },

  methods: {

    //Set the baseCurrency received from the NavComponent
    baseCurrency(target) {
      this.currency = target;
    }

  }
}
</script>

<style>

  html {
    font-size: 100%;
  }

  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  #app {
    font-family: 'Nunito', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    background-color: #2F2E32;
    height: 200vh;
    width: 100%;
    overflow-x: hidden;
  }


  @media screen and (max-width: 480px) {

    html {
      font-size: 70%;
    }

  }

  /*iPads, Tablets devices*/
  @media screen and (min-width: 481px) and (max-width: 768px) {

    html {
      font-size: 80%;
    }
   
    
  }

</style>
