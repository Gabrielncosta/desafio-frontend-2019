<template>
  <div class="home">
    <Header/>
    <Banner/>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Banner from '@/components/Banner.vue'

export default {
  name: 'home',
  components: {
    Header,
    Banner
  }
}
</script>
