<template>
  <div class="d-flex box align-items-start shadow-lg mb-5 bg-white rounded" style="flex-direction: column;">
    <div class="d-flex align-items-start p-4" style="flex-direction: column; flex-grow: 1;">
      <img :src="picture" class="img-fluid" alt="">
      <p class="purple bold">Eletrônicos</p>
      <p class="bold grey text-left">{{ name }}</p>
      <p class="text-left regular">Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore, quaerat.</p>
      <h6 class="bold grey">R${{ price }} </h6>
    </div>
    <button class="btn btncustom mx-auto purple bold py-3" style="width: 100%; height: 60px;">ADICIONAR AO CARRINHO</button>
  </div>
</template>

<script>

  export default{
      name: 'Product',
      props: [ 'picture', 'price', 'name'],
  }
</script>


<style lang="scss" scoped>
  .purple {
    color: #8e36b7;
  }

  .btncustom {
    font-size: .9em;
    border-top: 1px solid black;
  }

  .bold {
    font-family: 'SourceSansPro-Bold';
  }

  .grey {
    color: #434343;
  }

  .regular {
    font-family: 'SourceSansPro-Regular';
    color: #909090;
    line-height: 1em;
    font-size: .8em;
  }

  .btncustom:hover {
    background-color: #8e36b7;
    color: #fff;
    border: none;
  }

  hr {
    width: 100%;
  }
  
</style>
