<template>
    <header>
        <h1>Boolflix</h1>
    </header>
</template>
<script>
export default {
    name:'AppHeader',
    data(){
        return{

        }
    },
}
</script>
<style lang="scss" scoped>
     @use '../styles/partials/mixins' as*;
     @use '../styles/partials/variables' as*;

     header{
        height: 80px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: red;
        background-color: black;
     }
</style>