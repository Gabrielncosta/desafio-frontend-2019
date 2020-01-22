<template>
  <div class="home">
    <Header/>
    <Banner/>
    <search-bar/>
    <list/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'
import SearchBar from '@/components/SearchBar.vue'
import List from '@/components/List.vue'

export default {
  name: 'home',
  components: {
    Header,
    Banner,
    SearchBar,
    List
  }
}
</script>
