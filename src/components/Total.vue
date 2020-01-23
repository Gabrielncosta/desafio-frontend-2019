<template>
  <div>
    <div class="container">
      <div class="d-flex justify-content-around">
        <p class="tags">produtos</p>
        <p class="tags">quantidade</p>
        <p class="tags">valor unitário</p>
        <p class="tags">total</p>
      </div>
      <div class="d-flex justify-content around">
        <div class="d-flex flex-column">
          <p>Eletrônicos</p>
          <p>notebook</p>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
  export default{
      name: 'Total'
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
    font-family: 'SourceSansPro-  ';
  }

  .bold {
    font-family: 'SourceSansPro-Bold  ';
  }
  
  .border {
    border-top: 1px solid black;
  }

</style>
