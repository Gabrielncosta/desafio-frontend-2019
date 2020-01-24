<template>
  <div class="navbar-ow footer">
    <div class="container container-navbar">
      <img class="logo" src="../assets/images/logo-footer.png">
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
    height: 15vh;
  }

  .container{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }

  @media(max-width: 770px) {
    .footer {
      margin-top: 50px;
    }
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
