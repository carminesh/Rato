<template>

  <NavComponent></NavComponent>
  <MainComponent></MainComponent>
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
  }
}
</script>

<style>

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
  }
</style>
