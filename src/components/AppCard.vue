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
        {{ movie.title }}


    </li>
</template>


<style></style>