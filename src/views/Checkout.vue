<template>
  <div class="home">
    <Header/>
    <SignUp/>
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import SignUp from '@/components/SignUp.vue'
export default {
  name: 'Carrinho',
  components: {
    Header,
    Footer,
    SignUp
  }
}
</script>
