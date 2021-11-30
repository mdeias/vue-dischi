<template>
  <div>
    <Header @changeGenre="selectionGenre" :genresList="genres" />
    <Main :genreToSearch="genreSelected" @genresListed="genresToPops" />
  </div>
</template>

<script>
import Header from './components/Header';
import Main from './components/Main';


export default {
  name: 'App',

  components: {
    Header,
    Main
  },

  data(){
    return{
      genreSelected:'',
      genres: []
    };
  },

  methods:{

    selectionGenre(genre){
      this.genreSelected = genre;
    },

    genresToPops(arrGenres){
      console.log(arrGenres);
      this.genres = arrGenres;
    }
  }
}  
</script>

<style lang="scss">
@import '~@fontsource/montserrat/index.css';
@import './assets/style/generali.scss';
@import './assets/style/utilities.scss';
@import './assets/style/mixins.scss';

body{
  font-family: 'Montserrat', sans-serif;
}

</style>
