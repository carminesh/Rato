<template>

  <div class="main-container">
    <div class="first-section">
      <div class="text-container">
        <h1>
        Start to exchange your value right now
        </h1>
        <p>To get started enter the values below and calculate today’s exchange rates</p>
        <a id="exchange-redirect" href="">Exchange now</a>
      </div>
      <img src="../assets/hero.svg" alt="hero image">
    </div>

    <div class="second-section">
      <h1 id="exchange-text">Convert your value - 18th November</h1>
      <FormContainer></FormContainer>
    </div>
  </div>
  
</template>

<script>
import FormContainer from './FormContainer.vue'

export default {
  name: 'MainComponent',
  components: {
    FormContainer
  }
}
</script>

<style scoped>

  .main-container {
    width: 80%;
    height: 80%;
    margin: auto;
    display:flex;
    flex-direction: column;
    align-items: center;
  }

  .first-section {
    background-color: #2F2E32;
    color: white;
    width: 100%;
    height: 50%;
    display: flex;
    align-items: center;
  }

  .text-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    font-size: 1.6rem;
    width: 50%;
  }

  .text-container p {
    padding-top: 1rem;
  }

  .first-section img {
    margin: auto;
    height: 98%;
    object-fit: cover;
  }

  #exchange-redirect {
    font-size: 1.5rem;
    font-weight: 600;
    margin-top: 20px;
    background-color: #3872FF;
    text-decoration: none;
    color: white;
    width: 32%;
    padding: 0.8rem;
    border-radius: 10px;
    cursor: pointer;
  }

  .second-section {
    margin-top: 60px;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    width: 100%;
    height: 35%;
  }

  #exchange-text {
    font-size:  2.6rem;
    color: white;
  }



</style>
