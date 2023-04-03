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
        AppCard
    }
}

</script>

<template>
    <main>
        <section>
            <h3>Movies</h3>
            <ul>
                <AppCard v-for="(movie, index) in store.movies" :key="index" :movie="movie"></AppCard>



            </ul>
        </section>
    </main>
</template>


<style scoped>
ul {
    display: flex;
    flex-wrap: wrap;
}
</style>