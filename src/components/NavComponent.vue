<template>
  <div class="nav-container">
    <a href="#"><img id="logo" src="../assets/logo.svg" alt="logo"></a>
    <div class="base-currency">
      <h3>Base Currency</h3>
      <div class="currency">
        <h3>USD</h3>
      </div>
    </div>
  </div>
  
</template>

<script>

export default {
  name: 'NavComponent',
  
}
</script>

<style scoped>

  .nav-container {
    background-color: #2F2E32;
    min-height: 10%;
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
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .currency {
    display: flex;
    align-items: center;
    background-color: #ffff;
    margin-left: 20px;
    width: 100px;
    height: 45px;
    border-radius: 5px;
    color: #2F2E32;
  }

  .currency h3 {
    margin-left: 5px;
  }

</style>
