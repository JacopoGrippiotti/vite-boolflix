<template>
  <div class="films">
        <h1>Films</h1>
    <div class="films-container">
        <FilmElement v-for="film in filmList"
        :title="film.title"
        :originalTitle="film.original_title"
        :language="film.original_language"
        :vote="film.vote_count"
        :acceptedLanguages="acceptedLanguages"
          />
    </div>
  </div>
    
    
  <div class="series">
        <h1>Series</h1>
    <div class="series-container">
        <FilmElement v-for="series in seriesList"
        :title="series.name"
        :originalTitle="series.original_name"
        :language="series.original_language"
        :vote="series.vote_count"
        :acceptedLanguages="acceptedLanguages"
          />
    </div>
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
        filmList:Array,
        seriesList:Array
    },
    data(){
        return{
            acceptedLanguages:['it','en','es','nl','cs','pt','fr']
        }
    }
}
</script>

<style lang="scss" scoped>
    @use '../styles/partials/mixins' as*;
    @use '../styles/partials/variables' as*;

   

   div.films{
    width: 100%;
   }
    div.films-container{
        width: 90%;
        @include flex(row,space-between,wrap);
        margin: 0 auto;            
    }
    div.series-container{
        width: 90%;
        @include flex(row,space-between,wrap);
        margin: 0 auto;          
    }

    div.series{
        width: 100%;
    }
    h1{
        text-align: center;
        margin-top: 2px;
    }

</style>