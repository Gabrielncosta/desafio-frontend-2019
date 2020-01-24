<template>
  <tr class="borderbottom">
    <th scope="row">
      <Garbage @click="deleteProduct" class="icon"/>
      </th>
    <td class="padding">
      <p class="purple bold">Eletrônicos</p>
      <p class="bold">{{ list.name }}</p>
    </td>
    <td>
      <div class="input-group mb-3 mx-auto width">
        <div class="input-group-prepend">
          <span @click="subtraction" class="input-group-text btnwhite" id="basic-addon1">-</span>
        </div>
        <input v-model="quantity" @keypress="isNumber($event)" type="text" class="form-control inputform" aria-label="Username" aria-describedby="basic-addon1">
         <div class="input-group-prepend">
          <span @click="add" class="input-group-text btnwhite" id="basic-addon1">+</span>
        </div>
      </div>
    </td>
    <td><span class="bold"> R$ {{ list.price }} </span> à vista <br> ou 10x R$ {{ format(list.price) }} </td>
    <td><span class="bold"> R$ {{ list.price }} </span>à vista </td>
  </tr>

</template>

<script>
  
  import Garbage from '../assets/svg/garbage.svg';
  

  export default {
    name: 'Table',
    props: ['list'],
    components: {
      Garbage,
    },
    data() {
      return {
        quantity: this.list.quantity
      }
    },
    
  /*   mounted() {
      this.quantity = this.list.quantity;
    }, */
    methods: {
      isNumber(evt) {
        evt = (evt) ? evt : window.event;
        var charCode = (evt.which) ? evt.which : evt.keyCode;
        if ((charCode > 31 && (charCode < 49 || charCode > 57))) {
          evt.preventDefault();
        } else {
          return true;
        }
      },
      subtraction() {
        this.quantity--;
        let productsJson = [];
        productsJson = JSON.parse(localStorage.getItem('produtos'));
        let index = this.procurarIndice(productsJson, 'name', this.list.name);
        productsJson[index].quantity = this.quantity;
        this.saveProducts(productsJson);
        this.update();

      },
      add() {
        this.quantity++;
        let productsJson = [];
        productsJson = JSON.parse(localStorage.getItem('produtos'));
        let index = this.procurarIndice(productsJson, 'name', this.list.name);
        productsJson[index].quantity = this.quantity;
        this.saveProducts(productsJson);
        this.update();

        // no += jogar o valor do quantity
      },
      procurarIndice(arraySearch, atributo, valor){
        for(var i in arraySearch){
          var row = arraySearch[i];
          if(row[atributo]==valor){
            return i;
          }
        }
      },
      saveProducts(products) {
        const parsed = JSON.stringify(products);
        localStorage.setItem('produtos', parsed);
      },
      update() {
        this.$root.$emit('update');
      },
      format(value) {
      },
      deleteProduct() {
        this.quantity = 0;
        let productsJson = [];
        productsJson = JSON.parse(localStorage.getItem('produtos'));
        let index = this.procurarIndice(productsJson, 'name', this.list.name);
        productsJson[index].quantity = this.quantity;
        this.saveProducts(productsJson);
        this.update();
      },
    }
    
  }
     
</script>


<style lang="scss" scoped>

  td {
    font-family: 'SourceSansPro-Regular';
  }

  .icon {
    fill: #cfcfcf;
    cursor: pointer;
  }

  .btnwhite {
    background-color: white;
    cursor: pointer;
  }

  .width {
    width: 110px;
  }

  .padding {
    padding: 25px 0;
  }

  .borderbottom {
    border-bottom: 1px solid black;
  }

  .inputform {
    font-family: 'SourceSansPro-Bold';
  }

  .purple {
    color: #8e36b7;
    text-align: start;
  }

  .bold {
    font-family: 'SourceSansPro-Bold';
    text-align: start;
  }


</style>
