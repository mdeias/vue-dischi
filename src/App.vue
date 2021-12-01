<template>
  <div>
    <Header @newSelect="scegliGenere" />
    <Main @listaGeneri="elencoGeneri" :genereDaCercare="genereSelezionato"/>
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
      genereSelezionato: '',
      generi: []
    }
  },
  
  methods:{
    scegliGenere(genere){
      this.genereSelezionato = genere;
      console.log('App.vue ha ricevuto qualcosa da un evento (newSelect)', this.genereSelezionato);
    },
    elencoGeneri(generi){
      console.log(generi);
      this.genres = generi;
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
