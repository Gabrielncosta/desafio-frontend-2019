<template>
  <div>
      <carousel :per-page="1" :navigate-to="someLocalProperty" :mouse-drag="false">
      <slide class="banner-1">
        <div class="container containerbanner d-flex justify-content-end align-items-center">
          <div>
            <h2 class="bannertitle">Notebooks</h2>
            <p class="bannersubtitle">As melhores ofertas</p>
          </div>
        </div>
      </slide>
      <slide class="banner-2">
        <div class="container containerbanner d-flex justify-content-start align-items-center">
          <div>
            <h2 class="bannertitle">Smartphone</h2>
            <p class="bannersubtitle">Confira as últimas novidades</p>
          </div>
        </div>
      </slide>
    </carousel>
    </div>
</template>

<script>

  import { Carousel, Slide } from 'vue-carousel';

  export default{
      name: 'Banner',
      components: {
        Carousel,
        Slide
      },
      
  }
</script>


<style lang="scss" scoped>

  .banner-1 {
    background: rgb(142,54,183);
    background: linear-gradient(90deg, rgba(142,54,183,1) 6%, rgba(215,148,246,1) 70%); 
    height: 300px;
  }

  .banner-2 {
    background: #368eb7; /* Old browsers */
    background: -moz-linear-gradient(left, #368eb7 0%, #94f5f6 100%); /* FF3.6-15 */
    background: -webkit-linear-gradient(left, #368eb7 0%,#94f5f6 100%); /* Chrome10-25,Safari5.1-6 */
    background: linear-gradient(to right, #368eb7 0%,#94f5f6 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#368eb7', endColorstr='#94f5f6',GradientType=1 ); /* IE6-9 */
  }

  .containerbanner {
    height: 100%;
    h2, p {
      color: #fff;
    }

    .bannertitle {
      font-family: 'SourceSansPro-Bold';
      font-size: 3.5em;
    }

    .bannersubtitle {
      font-family: 'SourceSansPro-Bold';
      font-size: 1.5em;
    }
  }
  
</style>
