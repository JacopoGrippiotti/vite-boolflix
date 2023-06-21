<template>
    <div class="films-container">
        <FilmElement v-for="film in filmList"
          :title="film.title"
          :originalTitle="film.original_title"
          :language="film.original_language"
          :vote="film.vote_count"
          />
    </div>
</template>

<script>
import FilmElement from './FilmElement.vue';
export default {
    name:'FilmAdder',
    components:{
        FilmElement
    },
    props:{
        filmList:Array
    }
}
</script>
<style lang="scss" scoped>
    @use '../styles/partials/mixins' as*;
    @use '../styles/partials/variables' as*;
    div.films-container{
        width: 90%;
        @include flex(row,space-between,wrap);
        margin: 0 auto;             
    }

</style>