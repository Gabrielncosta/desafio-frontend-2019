<template>
  <div>
    <div class="container pt-5" style="height: 100%;">
    <table style="width: 100%;">
      <thead style="border-bottom: 1px solid black; ">
        <tr>
          <th scope="col" style="width: 50px;"></th>
          <th scope="col" style="width: 200px;">Produtos</th>
          <th scope="col">Quantidade</th>
          <th scope="col">Valor Unitário</th>
          <th scope="col">Total</th>  
        </tr>
      </thead>
      <tbody v-for="(item, i) in items" :key="i">
        <Table 
        :list="item"
        ></Table>
      </tbody>

    </table>
    </div>
  </div>
</template>

<script>
  import Table from './Table.vue'


  export default{
    name: 'Total',
    components: {
      Table,
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
    mounted() {
      /* this.produtos = JSON.parse(localStorage.getItem('produtos')) */
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
  
  .border {
    border-top: 1px solid black;
  }

  .icon {
    fill: #cfcfcf;
    
  }

</style>
