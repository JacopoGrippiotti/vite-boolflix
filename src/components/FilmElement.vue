<template>
    <div class="film-box">
        <h1>{{ title }}</h1>
        <h2>{{ originalTitle }}</h2>
        <p>{{ language}}</p>
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
    },
    data(){
        return{
            flag: ""
        }
    },
    methods:{
        filmAdder(){
            if(this.language === ''){
                return
            }
            else if (this.language !== 'it'){
                return language
            }
            else if(this.language === 'it'){
                this.flag = "../img/it.svg"
            }
        }
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
        justify-content: space-between;
        
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
            font-size: 1.3rem;
            margin-top: 2px;
        }

        h2{
            font-size: 1rem;
            margin-top: 2px;
        }

        p{
            margin-top: 2px;
        }

    }

    /* :class= "flag === 'it' ? 'language':'hidden'"*/
    
</style>