<template>
  <div class="navbar-ow">
    <div class="container container-navbar">
      <img class="logo" src="../assets/images/logo.png" alt="logo">
      <div class="elementos-navbar">
        <a class="produtos" target="_blank">Produtos</a>
        <Cart class="icon"/>
        <span class="carrinho"> {{ name }} </span>
          <!-- <input v-model="name"> -->
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
          name: ''
        }
      },
      components: {
        Cart
      },
      mounted() {
        if (localStorage.produtos) {
          let products = JSON.parse(localStorage.produtos);
          this.name = products.length;
          console.log(products);
        }
        this.$root.$on('update', () => {
          let products = JSON.parse(localStorage.produtos);
          this.name = products.length;
          
        })
      },
/*       computed: {
        itemsCarrinho: function() {
          let number = JSON.parse(localStorage.getItem('produtos'));
          let a = number.length;
          return a;
        }
      },
      methods() {
        
      } */
 /*      created() {
        let number = JSON.parse(localStorage.getItem('produtos'));
        this.itemsCarrinho = number.length;
        console.log(number);
      } */
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
