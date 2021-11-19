<template>

  <div class="main-container">
    <div class="first-section">
      <div class="text-container">
        <h1>
        Start to exchange your value right now
        </h1>
        <p>To get started enter the values below and calculate today’s exchange rates</p>
        <button class="redirect-btn" @click="location.href=FormContainer">Exchange now</button>
      </div>
    </div>

    <div class="second-section">
      <h1 id="exchange-text">Convert your value - {{date}}</h1>
      <FormContainer :currency="currency"></FormContainer>
    </div>
  </div>
  
</template>

<script>
import FormContainer from './FormContainer.vue'
import {gsap} from 'gsap'

export default {
  name: 'MainComponent',
  components: {
    FormContainer
  },

  props: {
    currency: {
      type: String,
      required: true
    }
  }, 
  
  computed: {

    //Calculate the exact date 
    date() {
      const months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"];
      const today = new Date();
      let domEnder = new Array( 'th', 'st', 'nd', 'rd', 'th', 'th', 'th', 'th', 'th', 'th' );
      let dayOfMonth = (today.getDate() < 10) ? '0' + today.getDate() + domEnder[today.getDate()] : today.getDate() + domEnder[parseFloat(("" + today.getDate()).substr(("" + today.getDate()).length - 1))];
      return `${dayOfMonth} ${months[today.getMonth()]} ${today.getFullYear()}`;
    }
    
  },

  mounted: function() {
  
    gsap.from('.first-section', {opacity: 0, duration: 2, ease: 'Power1.easeInOut'});
    gsap.from('.text-container', {x:-1000, duration: 1, ease: 'Power1.easeOut'})

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
    height: 60%;
    display: flex;
    align-items: center;
    background-image: url(../assets/hero2.png);
    background-repeat: no-repeat;
    background-position: 30vw -10px;
    background-size: contain;
    background-blend-mode: normal;
  }

  .text-container {
    margin-bottom: 90px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    font-size: 1.6rem;
    width: 60%;
  }

  .text-container p {
    padding-top: 1rem;
  }

  .redirect-btn {
    font-size: 1.3rem;
    background-color: #3872FF;
    margin-top: 20px;
    padding: 1rem;
    color: white;
    border: none;
    border-radius: 5px;
    width: 50%;
    cursor: pointer;
    transition: all 0.4s ease;
  }

  .redirect-btn:hover {
    background-color: #1e48b3;
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

  /* MEDIA QUERIES */

  /*Mobile devices*/
  @media screen and (max-width: 480px) {

    .main-container {
      width: 100%;
      height: 100%;
    }

    .first-section {
      margin-top: 50px;
      width: 100%;
      height: 42%;
      flex-direction: column;
      align-items: flex-start;
      background-image: url(../assets/hero2.png);
      background-repeat: no-repeat;
      background-position: 50px 100px;
      background-size: 110%;
      background-blend-mode: overlay;
    }

    .text-container {
      margin-left: 5%;
      justify-content: center;
      font-size: 1.5rem;
      width: 90%;
    }

    .text-container p {
      padding-top: 0.7rem;
    }

    .redirect-btn {
      background-color: #3872FF;
      margin-top: 20px;
      padding: 1rem;
      color: white;
      border: none;
      border-radius: 5px;
      width: 50%;
    }

    .first-section img {
      display: none;
    }

    .second-section {
      display: flex;
      align-items: flex-start;
      flex-direction: column;
      width: 90%;
      height: 37%;
    }

    #exchange-text {
      font-size:  3rem;
      color: white;
    }


  }

   /*iPads, Tablets devices*/
  @media screen and (min-width: 481px) and (max-width: 768px) {

    .first-section {
      height: 48%;
      background-image: url(../assets/hero2.png);
      background-repeat: no-repeat;
      background-position: 0px 40px;
      background-size: 100%;
      background-blend-mode: overlay;
    }

    .text-container {
      justify-content: center;
      font-size: 1.8rem;
      width: 90%;
    }

     
    .first-section img {
      display: none;
    }

    .second-section {
      display: flex;
      align-items: flex-start;
      flex-direction: column;
      width: 100%;
      height: 43%;
    }

    .redirect-btn {
      font-size: 1.5rem;
    }
    
  }

  /*Small screens, laptops*/
  @media screen and (min-width: 769px) and (max-width: 1024px) {

    .first-section {
      height: 53%;
       background-image: url(../assets/hero2.png);
      background-repeat: no-repeat;
      background-position: 0px 50px;
      background-size: 100%;
      background-blend-mode: overlay;
    }

    .text-container {
      margin-top: 150px;
      align-self: flex-start;
      justify-content: center;
      font-size: 1.5rem;
      width: 90%;
    }

    .text-container p {
      padding-top: 0.7rem;
    }

    .first-section img {
      display: none;
    }

    .second-section {
      height: 42%;
    }

    .redirect-btn {
      font-size: 1.3rem;
    }

  }

  /*Large screen*/
  @media screen and (min-width: 1025px) and (max-width:1400px) {
    .first-section {
      height: 53%;
      background-image: url(../assets/hero2.png);
      background-repeat: no-repeat;
      background-position: 8px 0px;
      background-size: 100% 100%;
      background-blend-mode: overlay;
    }

    .text-container {
      margin-top: 150px;
      align-self: flex-start;
      justify-content: center;
      font-size: 1.5rem;
      width: 90%;
    }

    .text-container p {
      padding-top: 0.7rem;
    }

    .first-section img {
      display: none;
    }

    .second-section {
      height: 42%;
    }

    .redirect-btn {
      font-size: 1.3rem;
    }
  }

  @media screen and (min-width: 2000px) {
    .first-section {
      background-image: url(../assets/hero2.png);
      background-repeat: no-repeat;
      background-position: 40vw -10px;
      background-size: contain;
      background-blend-mode: normal;
    }
  }

</style>
