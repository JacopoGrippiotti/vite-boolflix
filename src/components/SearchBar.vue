<template>
    <div class="searchBar-container">
        <input type="text" placeholder="insert film here" v-model="searchValue">
        <button @click="$emit('searched', searchValue)">search</button>
    </div>
</template>
<script>
export default {
    name:'SearchBar',
    emits:['searched'],
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

    div.searchBar-container{
        width: 100%;
        display: flex;
        justify-content: flex-end;
        padding: 20px;
    }
</style>