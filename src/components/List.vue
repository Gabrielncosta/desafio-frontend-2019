<template>

<div class="container">
  <div class="row d-flex justify-content-between">
   <div class="d-flex" style="width: 30%; align-items: stretch;" v-for="(produto, i) in produtos" :key="i">
     <Product 
      :picture="produto.picture"
      :name="produto.name"
      :price="produto.price"
    ></Product>
   </div>
  </div>
</div>


<!--  <div>
    <div class="container">
      <div class="row d-flex" style="align-items: stretch">
        <div class="col-md-4" v-for="(produto, i) in produtos" :key="i">
          <Product 
          :picture="produto.picture"
          :name="produto.name"
          :price="produto.price"
          ></Product>
        </div>
      </div>
    </div>
  </div> -->
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
      }),
      mounted() {
        axios.get("https://api.myjson.com/bins/9e9fl").then(response => {
            this.produtos = response.data;
            console.log(this.produtos)
        });
      }
    }
</script>


<style lang="scss" scoped>
.paddingchange {
  padding-right: 0px;
  padding-left: 0px;
}

.item {
  flex-grow: 1;
}
  
</style>
