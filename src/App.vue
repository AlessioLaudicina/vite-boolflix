<script>
import axios from 'axios';

import AppHeader from './components/AppHeader.vue';
export default {
  name: 'App',
  data() {
    return {

    }

  },
  components: {
    AppHeader
  },
  created() {

    axios.get('https://api.themoviedb.org/3/search/movie?api_key=7b2204b229e446d8aea432af312b142c&query=ritorno+al+futuro')
      .then(response => {
        console.log(response)
      })

  }
}

</script>

<template>
  <header>
    <AppHeader></AppHeader>
  </header>
</template>

<style lang="scss">
@use './styles/general.scss';
@use './styles/partials/variables.scss' as *;
</style>
