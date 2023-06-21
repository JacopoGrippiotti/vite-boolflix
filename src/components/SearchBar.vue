<template>
    <input type="text" placeholder="insert film here" v-model="searchValue">
    <button @click="$emit('searchedFilm',searchValue)">search</button>
</template>
<script>
export default {
    name:'SearchBar',
    data(){
        return{
            searchValue:""
        }
    },
    methods:{

    }
}
</script>
<style lang="scss" scoped>
    @use '../styles/partials/mixins' as*;
    @use '../styles/partials/variables' as*;
</style>