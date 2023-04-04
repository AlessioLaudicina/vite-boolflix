<script>
import { store } from '../store.js';
import AppCard from '../components/AppCard.vue';
import AppCardTvShow from '../components/AppCardTvShow.vue';
export default {
    name: 'AppMain',
    data() {
        return {
            store
        }
    },
    components: {
        AppCard,
        AppCardTvShow
    }
}

</script>

<template>
    <section>
        <h3 class="text-white pt-3">Movies</h3>
        <ul>
            <AppCard v-for="(movie, index) in store.movies" :key="movie.id" :movie="movie"></AppCard>
        </ul>
    </section>

    <section>
        <h3 class="text-white pt-3">TV Shows</h3>
        <ul>
            <AppCardTvShow v-for="(movie, index) in store.tvShow" :key="movie.id" :movie="movie"></AppCardTvShow>


        </ul>

    </section>
</template>


<style scoped>
ul {
    display: flex;
    flex-wrap: wrap;
}
</style>