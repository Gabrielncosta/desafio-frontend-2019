<template>
  <div class="home">
    <Header/>
    <Total/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import Total from '@/components/Total.vue'
export default {
  name: 'Carrinho',
  components: {
    Header,
    Footer,
    Total
  }
}
</script>
