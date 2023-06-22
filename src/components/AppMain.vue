<template>
    <main>
        <SearchBar @searched="newCall"/>
        <FilmAdder 
        :filmList="filmList"/>
    </main>
</template>

<script>
import SearchBar from './SearchBar.vue';
import FilmAdder from './FilmAdder.vue';
import axios from 'axios';
export default {
    name:'AppMain',
    components:{
        SearchBar,
        FilmAdder
    },
    data(){
        return{
            apiUrl:'https://api.themoviedb.org/3/search/movie?api_key=4e1e3ce8a9a8b7f034096dab8c5b88cc&query=',
            filmList:[]
        }
    },
    methods:{
        newCall(filmString){
            axios.get(this.apiUrl + filmString)
            .then((response) => {
                this.filmList = response.data.results
                console.log(this.filmList)
            })
            } 
    }
}
</script>
<style lang="scss" scoped>
    @use '../styles/partials/mixins' as*;
    @use '../styles/partials/variables' as*;

    main{
        display: flex;
        flex-wrap: wrap;
        background-color: red;
    }
</style>