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

    performSearch() {
      this.getMovies();
      this.getTvShow();

    },


    getMovies() {
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=${this.store.ApiToken}&query=${this.store.search}`)
        .then(response => {
          this.store.movies = response.data.results;
        });
    },
    getTvShow() {
      axios.get(`https://api.themoviedb.org/3/search/tv?api_key=${this.store.ApiToken}&query=${this.store.search}`)
        .then(response => {
          this.store.tvShow = response.data.results;
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
    <AppHeader @doSearch="performSearch"></AppHeader>
  </header>

  <main>
    <div class="container">
      <AppMain></AppMain>

    </div>


  </main>
</template>

<style lang="scss">
@use './styles/general.scss';
@use './styles/partials/variables.scss' as *;

body {
  background-color: $secondary-color;
}
</style>
