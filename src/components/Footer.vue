<template>
  <div class="navbar-ow">
    <div class="container container-navbar">
      <img class="logo" src="../assets/images/logo.png">
    </div>
  </div>
</template>

<script>
  export default{
      name: 'Header'
  }
</script>


<style lang="scss" scoped>

  .navbar-ow{
    padding: 20px 0;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    font-family: 'Nunito', regular;
    background-color: #bbbbbb;
  }

  .container{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }


  @media (max-width: 550px){
    .logo{
      width: 30%;
    }
  }

  @media (max-width: 450px){

    .logo{
      width: 30%;
    }

  }

  @media (max-width: 450px){

    .logo {
      width: 25%;
    }

  }

</style>
