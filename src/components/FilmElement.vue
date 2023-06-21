<template>
    <div class="film-box">
        <h1>{{ title }}</h1>
        <h2>{{ originalTitle }}</h2>
        <p class="language">{{ language }}</p>
        <p class="vote"> {{ vote }}</p>
    </div>
</template>

<script>
export default {
    name:'FilmElement',
    props:{
        title:String,
        originalTitle:String,
        language:String,
        vote: Number
    }
}
</script>
<style lang="scss" scoped>
  @use '../styles/partials/mixins' as*;
  @use '../styles/partials/variables' as*;

    div.film-box{
        width: calc((100% / 5) - 20px);
        display: flex;
        flex-direction: column;
        border: 1px solid black;
        text-align: center;
        justify-content: space-between
        ;
          
        h1{
            font-size: 1.3rem;
            
        }

        h2{
            font-size: 1rem;
        }


    }
</style>