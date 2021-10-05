<template>
  <div id="app">
    <Header />
    <Main :movies="films"/>
  </div>
</template>

<script>
import axios from 'axios';
import Main from './components/Main.vue'
import Header from './components/Header.vue'


export default {
  name: 'App',
  components: {
    Main,
    Header,

  },
  data: function(){
    return{
        apiUrl: 'https://api.themoviedb.org/3/search/movie',
        apiKey: '220d2b0d1afd421bec306147ec0fae6c',
        films: [],
        searchField: '',

    }
  },
  methods:{
    searchMovie: function(searchField){
      console.log(searchField);
      if(searchField.length > 1){

        axios.get(this.apiUrl,{
          params: {
            api_key: this.apiKey,
            query: searchField,
          }
          }).then(
          (risultato) =>{
            this.films = [...risultato.data.results];
            console.log('array films', this.films);
          })
          .catch(
            (errore)=>{
              console.warn("errore nella richiesta dell'API: ", errore);
            }
          )
      }
    },
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
