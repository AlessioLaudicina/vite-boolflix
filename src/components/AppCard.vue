<script>
export default {
    name: 'AppCard',
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
                    <img src="" alt="Movie" style="width:300px;height:300px;">
                </div>
                <div class="flip-card-back">
                    <h3> {{ movie.title }}</h3>
                    <p>{{ movie.original_title }}</p>
                    <p>{{ movie.original_language }}</p>
                    <p>{{ movie.vote_average }}</p>
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
</style>