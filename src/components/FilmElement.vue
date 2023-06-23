<template>
    <div class="film-box">
      <div :class="(active === true) ? 'hidden': 'img-container'" @click="active = true">
        <img :class="(active === true) ? 'hidden': ''" :src="getImagePath(imagePath)" alt="">
      </div>
      <div :class="(active === true) ? 'description-container' : 'hidden'" @click="active = false">
        <h1>{{ title }}</h1>
        <h2>{{ originalTitle }}</h2>
        <img class="flag" v-if="flag === language" :src="getFlagPath(language)" alt="">
        <p v-else>{{ language}}</p>
        <p class="vote"> {{ vote }}</p>
      </div>
        
    </div>
</template>  

<script>
export default {
    name:'FilmElement',
    props:{
        title:String,
        originalTitle:String,
        language:String,
        vote: Number,
        acceptedLanguages: Array,
        imagePath:String
    },
    data(){
        return{
            flag: this.filmAdder(this.language,this.acceptedLanguages),
            active:false
        }
    },
    methods:{
        filmAdder(language,acceptedLanguages){
            console.log(acceptedLanguages)
            console.log(language)
            if (acceptedLanguages.includes(language)){
                
                return language
            }
            else{
                return false
            }
        },
        getFlagPath(language){
            return new URL (`../img/${language}.svg`, import.meta.url).href;
        },
        getImagePath(imagePath){
            return `https://image.tmdb.org/t/p/w342/${imagePath}`
        }
    }
}
</script>
<style lang="scss" scoped>
  @use '../styles/partials/mixins' as*;
  @use '../styles/partials/variables' as*;

    div.film-box{
        margin-top: 25px;
        width: calc((100% / 5) - 20px);
        border: 1px solid black;
        color: white;
        div.img-container{
            height: 100%;
            width: 100%;

            img{
                height: 100%;
                width: 100%;
            }
        }
        div.description-container{
            height: 100%;
            width: 100%;
            display: flex;
            flex-direction: column;
            justify-content: space-evenly;
            align-items: center;
            background-color: lightgray;
        }
        img.flag{
            width: 30px;
            height: 30px;
        }
    
        
        h1{
            font-size: 1rem;
        }

        h2{
            font-size: 0.9rem;
            
        }

        .hidden{
            display: none ;
        }
        
    }

    
</style>