<template>
  <div class="home">
    <Header/>
    <Banner/>
    <search-bar/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'
import SearchBar from '@/components/SearchBar.vue'

export default {
  name: 'home',
  components: {
    Header,
    Banner,
    SearchBar
  }
}
</script>
