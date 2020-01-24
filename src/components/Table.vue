<template>
  <tr style="border-bottom: 1px solid black;">
    <th scope="row">
      <Garbage class="icon"/>
      </th>
    <td>
      <p class="purple bold">Eletrônicos</p>
      <p class="bold">{{ list.name }}</p>
    </td>
    <td>
      <div class="input-group mb-3 mx-auto" style="width: 110px;">
        <div class="input-group-prepend">
          <span @click="subtraction" class="input-group-text btnwhite" id="basic-addon1">-</span>
        </div>
        <input v-model="quantity" @keypress="isNumber($event)" type="text" class="form-control" aria-label="Username" aria-describedby="basic-addon1">
         <div class="input-group-prepend">
          <span @click="add" class="input-group-text btnwhite" id="basic-addon1">+</span>
        </div>
      </div>
    </td>
    <td>R$ {{ list.price }} à vista <br> ou 10x R$ {{ parseInt(list.price) / 10 }} </td>
    <td>@mdo</td>
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
    }
  }
     
</script>


<style lang="scss" scoped>
  .icon {
    fill: #cfcfcf;
  }

  .btnwhite {
    background-color: white;
    cursor: pointer;
  }

</style>
