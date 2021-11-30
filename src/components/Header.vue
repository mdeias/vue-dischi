<template>
  <header>
      <img src="../assets/img/logo-spotify.png" alt="">
      <select 
      v-model="genre"
      @change="$emit('changeGenre',genre)">
      <option value="" selected>Seleziona un genere</option>
      <option value="genre"
        v-for="(genre, index) in genresList"
        :key="index">
        {{genre}}
      </option>
      </select>
  </header>
</template>

<script>
export default {
    name: 'Header',
    props:{
        genresList: Array
    },
    data(){
        return{
            genre:''
        }
    },

     methods: {}
}
   

</script>

<style lang="scss">
@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';

header{
    @include center(between);
    height: 51px;
    background-color: #2D3C47;
    padding: 20px;
    img{
        width: 35px;
    }
}

</style>