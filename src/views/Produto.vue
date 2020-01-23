<template>
  <div class="home">
    <Header/>
    <Banner/>
    <list/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'
/* import SearchBar from '@/components/SearchBar.vue' */
import List from '@/components/List.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'Produto',
  components: {
    Header,
    Banner,
 /*    SearchBar, */
    List,
    Footer
  }
}
</script>
