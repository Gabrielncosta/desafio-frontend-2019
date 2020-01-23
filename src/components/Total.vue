<template>
  <div>
    <div class="container pt-5" style="height: 100%;">
      <table class="table">
        <thead>
          <tr>
            <th scope="col" style="width: 50px;"></th>
            <th scope="col" style="width: 200px;">Produtos</th>
            <th scope="col">Quantidade</th>
            <th scope="col">Valor Unitário</th>
            <th scope="col">Total</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row"><Garbage class="icon"/></th>
            <td>
              <p class="purple bold">Eletrônicos</p>
              <p class="bold">Notebook Acer <br> Aspire  e3 a515</p>
            </td>
            <td>Otto</td>
            <td>@mdo</td>
            <td>@mdo</td>
          </tr>
          <tr>
            <th scope="row"><Garbage class="icon"/></th>
            <td>Jacob</td>
            <td>Thornton</td>
            <td>@fat</td>
            <td>@fat</td>
          </tr>
          <tr>
            <th scope="row"><Garbage class="icon"/></th>
            <td>Larry</td>
            <td>the Bird</td>
            <td>@twitter</td>
            <td>@twitter</td>
          </tr>
        </tbody>
      </table>
    </div>
      <!-- <div class="d-flex justify-content-around">
        <p class="tags">produtos</p>
        <p class="tags">quantidade</p>
        <p class="tags">valor unitário</p>
        <p class="tags">total</p>
      </div>
      <div class="d-flex justify-content-around" style="border-top: 1px solid black;">
        <div class="d-flex flex-row align-items-center">
          <Garbage class="icon"/>
          <div class="d-flex flex-column align-items-start">
            <p class="purple bold">Eletrônicos</p>
            <p class="bold">Notebook Acer <br> Aspire  e3 a515</p>
          </div>
        </div>
        
        <div class="d-flex flex-column">
         <p>Eletrônicos</p>
        </div>
        <div class="d-flex flex-column">
         <p>Eletrônicos</p>
        </div>
        <div class="d-flex flex-column">
         <p>Eletrônicos</p>
        </div>
      </div>
    </div>
 -->
  </div>
</template>

<script>
  import Garbage from '../assets/svg/garbage.svg';


  export default{
    name: 'Total',
    components: {
      Garbage
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
