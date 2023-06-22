<template>
    <input type="text" placeholder="insert film here" v-model="searchValue">
    <button @click="$emit('searched', searchValue)">search</button>
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
</style>