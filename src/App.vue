<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  name: 'App',
  data() {
    return {
      store
    }

  },
  methods: {
    getMovies() {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.store.ApiToken}&query=${this.store.search}`)
        .then(response => {
          console.log(response);
          this.store.movies = response.data.results;
        });


    }
  },
  components: {
    AppHeader,
    AppMain
  },

}

</script>

<template>
  <header>
    <AppHeader @doSearch="getMovies"></AppHeader>
  </header>

  <main>
    <AppMain></AppMain>

  </main>
</template>

<style lang="scss">
@use './styles/general.scss';
@use './styles/partials/variables.scss' as *;
</style>
