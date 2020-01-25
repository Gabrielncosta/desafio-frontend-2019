<template>
  <div class="height">
    <div class="container pt-5">
    <table style="width: 100%;">
      <thead class="borderbottom">
        <tr class="tr">
          <th scope="col" class="col-1"></th>
          <th class="category col-2" scope="col">Produtos</th>
          <th class="category" scope="col">Quantidade</th>
          <th class="category" scope="col">Valor Unitário</th>
          <th class="category" scope="col">Total</th>  
        </tr>
      </thead>
      <tbody v-for="(item, i) in items" :key="i">
        <Table 
        :list="item"
        ></Table>
      </tbody>
    </table>
    </div>
    <div class="navbar-ow">
      <div class="container container-navbar">
        <div class="d-flex flex-row align-items-center cursor" @click="ClearCart">
          <Garbage style="margin-bottom: 40px;" class="icon"/>
          <a class="produtos" target="_blank">Limpar Carrinho</a>
        </div>
        <div class="elementos-navbar pointer justify-content-around" @click="RouteCart">
          <div class="d-flex justify-content-end">
            <button @click="RouteBack" type="submit" class="btn btn-buy grey">Continuar comprando</button>
          </div>
          <div class="d-flex justify-content-end">
            <button @click="RouteCheckout" type="submit" class="btn btn-buy purple">Concluir compra</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Table from './Table.vue'
  import Garbage from '../assets/svg/garbage.svg';

  export default{
    name: 'Total',
    components: {
      Table,
      Garbage
    },
    data() {
      return {
        items: [],
      }
    },
    created() {
      let json = localStorage.getItem('produtos')
      let myJson = JSON.parse(json)
      let jsonSize = Object.keys(myJson).length;
      
      for(let i = 0; i < Math.ceil(jsonSize); i++) {
        this.items.push({
          name: myJson[i].name, price: myJson[i].price, quantity: myJson[i].quantity,
        });
      }
    },
    methods: {
      RouteCheckout() {
        this.$router.push('/checkout');
      },
      RouteBack() {
        this.$router.push('/');
      },
      ClearCart() {
        localStorage.clear();
      }
    }
  }
</script>


<style lang="scss" scoped> 

  .purple {
    color: #8e36b7;
  }

  .grey {
    color: #434343;
  }

  .tags {
    text-transform: uppercase;
    font-family: 'SourceSansPro-Black';
  }

  .bold {
    font-family: 'SourceSansPro-Bold';
  }

  .borderbottom {
    border-bottom: 1px solid black; 
  }
  
  .border {
    border-top: 1px solid black;
  }

  .icon {
    fill: #cfcfcf;
  }

  .tr {
    height: 70px;
  }

  .col1 {
    width: 50px;
  }

  .col-2 {
    width: 200px;
  }

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

  .category {
    text-transform: uppercase;
    margin-bottom: 50px !important;
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

  .grey {
    background-color: #cfcfcf;
    color: #434343;
  }

  .btn-buy {
    font-family: 'SourceSansPro-Regular';
    width: 225px;
    height: 6vh;
    border-color: none !important; 
  }

  .purple {
    border-color: #8e36b7;
    background-color: #8e36b7;
    color: #fff;
    margin-left: 25px;
  }

  .cursor {
    cursor: pointer;
  }

  @media (max-width: 770px) {
    .height {
      height: auto;
    }
  }

</style>
