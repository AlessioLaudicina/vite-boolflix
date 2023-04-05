<script>
import { store } from '../store.js';
export default {
    name: 'AppCard',
    data() {
        return {
            store,
            availableFlags: ['en', 'it']
        }
    },
    methods: {
        getImageUrl(path) {
            return new URL(path, import.meta.url).href
        },
        getTitle() {
            if (this.movie.title) {
                return this.movie.title
            } else {
                return this.movie.name
            }
        },
        getOriginalTitle() {
            if (this.movie.original_title) {
                return this.movie.original_title
            } else {
                return this.movie.original_name
            }

        },
        getRating() {
            return Math.ceil(this.movie.vote_average / 2);
        },



    },
    props: {
        movie: Object
    }
}

</script>

<template>
    <li>
        <div class="flip-card">
            <div class="flip-card-inner">
                <div class="flip-card-front">
                    <img :src="store.imageUrl + movie.poster_path" alt="Movie" style="width:300px;height:300px;">
                </div>
                <div class="flip-card-back">
                    <h6> <span>Titolo: </span>{{ getTitle() }}</h6>
                    <p><span>Titolo originale: </span>{{ getOriginalTitle() }}</p>
                    <span>Paese: </span>
                    <img :src="getImageUrl(`../assets/flags/${movie.original_language}.png`)" class="flags"
                        v-if="availableFlags.includes(movie.original_language)" alt="Lingua">
                    <p v-else>{{ movie.original_language }} </p>

                    <div style="padding: 5px;">
                        <span>Valutazione: </span>

                        <i v-for="i in 5" class=" fa-star" :key="i"
                            :class="i <= getRating() ? 'fa-solid' : 'fa-regular'"></i>
                    </div>
                    <span>Trama: </span>
                    <p style="text-align: justify;">{{ movie.overview }}</p>

                </div>
            </div>
        </div>


    </li>
</template>


<style scoped>
.flip-card {
    background-color: transparent;
    width: 300px;
    height: 300px;
    perspective: 1000px;
    overflow: scroll;
}

.flip-card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.flip-card:hover .flip-card-inner {
    transform: rotateY(180deg);
}

.flip-card-front,
.flip-card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden;
    backface-visibility: hidden;
}

.flip-card-front {
    background-color: #bbb;
    color: black;
}

.flip-card-back {
    background-color: black;
    color: white;
    transform: rotateY(180deg);


}

li {
    list-style: none;
    margin: 5px;
}

h6 {
    padding: 10px 0;
}

span {
    font-weight: bolder;
}

p {
    font-size: 0.7rem;
    padding: 0 15px;

}

.flags {
    width: 30px;
    padding: 5px;
}
</style>