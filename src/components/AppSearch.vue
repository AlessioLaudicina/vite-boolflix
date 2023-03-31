<script>
export default {
    name: 'AppSearch',
    data() {
        return {

        }
    },
}
</script>

<template>
    <div class="search-container mx-2">
        <div class="row">

            <div class="col-9">
                <input type="text" class="form-control" placeholder="Search Movie or TV Show">
            </div>


            <div class="col-3">
                <button class="btn jt-btn px-4">Search</button>
            </div>

        </div>
    </div>
</template>


<style lang="scss" scoped>
@use "../styles/partials/variables" as *;


.jt-btn {
    background-color: $primary-color;
    color: white;

    &:hover {
        background-color: $primary-color;
        opacity: 0.7;
    }
}
</style>