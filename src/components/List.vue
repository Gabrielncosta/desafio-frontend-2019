<template>
<div>
  <div class="navbar-ow">
    <div class="container shadow bg-white rounded container-navbar">
      <p class="produto">Encontre seu produto
      </p>
      <div class="elementos-navbar">
      <form>
        <input type="text" v-on:input="filtered" v-model="search" class="form-control" placeholder="Pesquisar...">
      </form>
      <i class="fa fa-search icon"></i>
      </div>
    </div>
  </div>
  
  <div class="container">
    <div class="row d-flex justify-content-between rowbox">
    <div class="d-flex stretch" v-for="(produto, i) in filteredProducts" :key="i">
      <Product 
        :produto="produto"
      ></Product>
    </div>
    </div>
  </div>
</div>
</template>

<script>

  import Product from './Product.vue'
  const axios = require('axios');


  export default{
      name: 'List',
      components: {
        Product,
      },
      data: () => ({
        produtos: "",
        filteredProducts: [],
        search: ""
      }),
      mounted() {
        axios.get("https://api.myjson.com/bins/9e9fl").then(response => {
            this.produtos = response.data;
            this.filteredProducts = this.produtos;
        });
      },
      methods: {
        filtered: function(){
          this.filteredProducts = this.produtos.filter((produto) => {
            let str = produto.name.toUpperCase();
            let search = this.search.toUpperCase();
            return str.match(search);
        })
      },
     /*  computed: {
        filteredProducts: function(){
           return this.produtos.filter((produto) => {
            let str = produto.name.toUpperCase();
            let search = this.search.toUpperCase();
            return str.match(search);
          })
        } */
      }
    }
</script>


<style lang="scss" scoped>

  .paddingchange {
    padding-right: 0px;
    padding-left: 0px;
  }

  /* .rowbox {
    width: 100%;
  } */

  .item {
    flex-grow: 1;
  }

  form {
    width: 100%;
  }

  .stretch {
    width: 30%;
    align-items: stretch;
  }

  .container-navbar {
    height: 100px;
  }

  .navbar-ow{
    padding: 20px 0;
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

  .produto {
    margin-bottom: 0px;
    color: #909090;
    font-family: 'SourceSansPro-Bold';
  }


  .produtos{
    font-size: 16px;
    color: #909090;
    margin-right: 20px;
  }

  .elementos-navbar{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    align-items: center;
    width: 80%;
  }

  .icon {
    color: white;
    background-color: #8e36b7;
    width: 40px;
    height: 100%;
    padding: 6px;
    border-radius: 4px;
    position: relative;
    right: 35px;
    cursor: pointer;
  }

  @media(max-width: 770px) {
    .stretch {
      width: 100%;
      padding-left: 50px;
      padding-right: 50px;
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
