<template>
  <div class="navbar-ow">
    <div class="container container-navbar">
      <img class="logo pointer" @click="RouteMain" src="../assets/images/logo.png" alt="logo">
      <div class="elementos-navbar pointer" @click="RouteCart">
        <a class="produtos" target="_blank">Produtos</a>
        <Cart class="icon"/>
        <span class="carrinho" >{{ cartNumber }} </span>
      </div>
    </div>
  </div>
</template>

<script>
  import Cart from '../assets/svg/shopping-cart.svg';
  
  export default{
      name: 'Header',
      data() {
        return {
          items: 0,
          cartNumber: ''
        }
      },
      methods: {
        RouteCart() {
          this.$router.push('/carrinho');
        },
        RouteMain() {
          this.$router.push('/');
        },
        somaCarrinho(products) {
          let count = 0;
          for(let i in products) {
            count += products[i].quantity; 
          }
          return count;
        }
      },
      components: {
        Cart
      },
      mounted() {
        if (localStorage.produtos) {
          let products = JSON.parse(localStorage.produtos);
          this.cartNumber = this.somaCarrinho(products)
        }
        this.$root.$on('update', () => {
          let products = JSON.parse(localStorage.produtos);
          this.cartNumber = this.somaCarrinho(products)
          
        })
      },
  }
</script>


<style lang="scss" scoped>

  .navbar-ow{
    padding: 30px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    font-family: 'Nunito', regular;
    height: 15vh;
  }

  .container{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  .icon {
    fill: #8e36b7;
  }

  .produtos{
    font-size: 16px;
    color: #909090;
    margin-right: 20px;
    font-family: "SourceSansPro-Black";
  }

  .elementos-navbar{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
  }

  .pointer {
    cursor: pointer;
  }

  .carrinho {
    background-color: #e31424 !important;
    border-radius: 50%;
    color: #fff;
    width: 25px; 
    font-family: "SourceSansPro-Black"; 
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

    .produtos{
      margin-right: 8px;
      font-size: 14px;
    }
  }

  @media (max-width: 450px){

    .logo {
      width: 25%;
    }

    .produtos{
      font-size: 13px;
    }

  }


  @media (max-width: 330px){
    .produtos{
      font-size: 11px;
    }
  }

</style>
