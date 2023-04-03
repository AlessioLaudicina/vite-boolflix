<script>
import { store } from '../store.js';
export default {
    name: 'AppHeader',
    data() {
        return {
            store
        }

    },


}
</script>

<template>
    <div class="jt-container p-5">
        <h1>BOOTFLIX</h1>
        <div class="search-container mx-2">
            <div class="row">

                <div class="col-9">
                    <input @keyup.enter="$event => $emit('doSearch')" type="text" class="form-control"
                        placeholder="Search Movie or TV Show" v-model="store.search">
                </div>


                <div class="col-3">
                    <button @click="$event => $emit('doSearch')" class="btn jt-btn px-4">Search</button>
                </div>

            </div>
        </div>

    </div>
</template>

<style lang="scss" scoped>
.jt-container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    background-color: #000000;

    h1 {
        display: flex;
        align-items: center;
        color: #E50815;
    }
}

.jt-btn {
    background-color: #E50815;
    color: white;

    &:hover {
        background-color: #E50815;
        opacity: 0.7;
    }
}
</style>