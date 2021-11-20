<template>

  <div class="footer-container">
    <div class="footer">
        <h3>@Carmine Fabbri 2021 - 2022</h3>
        <a href="https://github.com/carminesh/Rato"><i class="fab fa-github-square"></i></a>
    </div>
  </div>

</template>

<script>

export default {
  name: 'FooterComponent',
  
}
</script>

<style scoped>

  .footer-container {
    color: rgb(240, 240, 240);
    position: absolute;
    bottom: -100vh;
    left: 0;
    width: 100%;
    height: 15%;
    max-height: 15%;
    background-color: #1d1c1e;
  }

  .footer {
    margin: auto;
    height: 100%;
    width: 80%;
    display: flex;
    align-items: center;
  }

  .footer a {
    text-decoration: none;
  }

  i {
    color: white;
    padding-left: 20px;
    font-size: 3rem;
    text-decoration: none;
  }

  /* #footer {
    pointer-events: none;
    bottom: 0;
    left: 0;
    object-fit: cover;
    z-index: 1;
    width: 100%;
  }

  #mobile-footer { 
    display: none;
  } */

  /* MEDIA QUERIES */

  /*Mobile devices*/
  @media screen and (max-width: 480px) {

    .footer-container {
      bottom: -170vh;
      height: 10%;
      max-height: 10%;
    }
    

  }

   /*iPads, Tablets devices*/
  @media screen and (min-width: 481px) and (max-width: 768px) {

    .footer-container {
      height: 10%;
      max-height: 10%;
    }

  }

  /*Small screens, laptops*/
  @media screen and (min-width: 769px) and (max-width: 1324px)  {

    .footer-container {
      height: 10%;
      max-height: 10%;
    }
  }

  /*Large screen*/
  @media screen and (min-width: 1025px) and (max-width:1400px) {
    .footer-container {
      height: 12%;
      max-height: 12%;
    }
  }
  
  @media screen and (min-width: 1401px) {
    .footer-container {
      height: 12%;
      max-height: 12%;
    }
  }

</style>
