<template>
  
  <img id="footer" src="../assets/footer.svg" alt="footer image">
  <img id="mobile-footer" src="../assets/mobileFooter.svg" alt="footer image">

</template>

<script>

export default {
  name: 'FooterComponent',
  
}
</script>

<style scoped>

  #footer {
    pointer-events: none;
    bottom: 0;
    left: 0;
    object-fit: cover;
    z-index: 1;
    width: 100%;
  }

  #mobile-footer { 
    display: none;
  }

  /* MEDIA QUERIES */

  /*Mobile devices*/
  @media screen and (max-width: 480px) {

    #mobile-footer {
      display: block;
      pointer-events: none;
      bottom: 10%;
      left: 0;
      object-fit: cover;
      z-index: 1;
      width: 120%;
    }

    #footer {
      display: none
    }

  }
  
</style>
