<script>
import { store } from '../store.js';
import AppCard from '../components/AppCard.vue';
export default {
    name: 'AppMain',
    data() {
        return {
            store
        }
    },
    components: {
        AppCard,

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
            <AppCard v-for="(serie, index) in store.tvShow" :key="index" :movie="serie"></AppCard>


        </ul>

    </section>
</template>


<style scoped>
ul {
    display: flex;
    flex-wrap: wrap;
}
</style>