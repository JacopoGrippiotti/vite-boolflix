<template>
    <div class="film-box">
        <h1>{{ title }}</h1>
        <h2>{{ originalTitle }}</h2>
        <img v-if="flag === language" :src="getImagePath(language)" alt="">
        <p v-else>{{ language}}</p>
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
        vote: Number,
        acceptedLanguages: Array
    },
    data(){
        return{
            flag: this.filmAdder(this.language,this.acceptedLanguages)
            
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
        getImagePath(language){
            return new URL (`../img/${language}.svg`, import.meta.url).href;
        }
    }
}
</script>
<style lang="scss" scoped>
  @use '../styles/partials/mixins' as*;
  @use '../styles/partials/variables' as*;

    div.film-box{
        margin-top: 10px;
        width: calc((100% / 5) - 20px);
        height: 200px;
        display: flex;
        flex-direction: column;
        border: 1px solid black;
        text-align: center;
        justify-content: space-between;
        align-items: center;
        
        img{
            width: 30px;
            height: 30px;
        }
        .language{
            display: block;
        }
        .flag{
            display: block;
        }
        .hidden{
        display: none;
        }
        h1{
            font-size: 1rem;
        }

        h2{
            font-size: 0.9rem;
            
        }

        
    }

    /* :class= "flag === 'it' ? 'language':'hidden'"*/
    
</style>