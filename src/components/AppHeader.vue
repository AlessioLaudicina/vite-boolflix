<script>
import AppSearch from './AppSearch.vue';
export default {
    name: 'AppHeader',
    data() {

    },
    components: {
        AppSearch,
    }

}
</script>

<template>
    <div class="jt-container p-5">

        <AppSearch></AppSearch>

    </div>
</template>

<style lang="scss" scoped>
.jt-container {
    width: 100%;
    display: flex;
    justify-content: space-between;
}
</style>