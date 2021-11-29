<template>
  <main>
      <SearchBar @inviaRicerca="eseguiRicerca"/>
      <div v-if="loaded" class="contenitore">
          <Card
          v-for="card in filtraCarte"
          :key="card.id"
          :card="card"
          />
      </div>
      <div v-else
      class="caricamento">
      <div class="lds-ripple"><div></div><div></div></div>
      <h1>LOADING</h1>
      </div>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './Card';
import SearchBar from './SearchBar';

export default {
    name: 'Main',
    components:{
        Card,
        SearchBar
    },

    data(){

        return{
            carte: [],
            loaded: false,
            testoUtente: ''  
        }

    },

    computed:{
        filtraCarte(){
            if(this.testoUtente === ''){
                return this.carte;
            }
             const carteFiltrate = this.carte.filter(item => {
                 return item.genre.toUpperCase().includes(this.testoUtente.toUpperCase())
             });
             return carteFiltrate;
        }
    },

    methods:{
        eseguiRicerca(text){
            this.testoUtente = text;
        },

        getApi(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(r => {
                    
                    this.carte = r.data.response;
                    console.log(this.carte);
                    this.loaded = true;
                })
                .catch(e => {
                    console.log(e);
                })
        }
    },

    mounted(){
        this.getApi();
    }
}
</script>

<style lang="scss">
@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';

main{
    position: relative;
    background-color: #1E2C3B;
    height: calc(100vh - 51px);
    padding: 72px;
    .contenitore{
        @include center (between);
        flex-wrap: wrap;
    }
    .caricamento{
        @include center();
        flex-direction: column;
        color: white;
        position: absolute;
        top: 30%;
        left: 43%;
        .lds-ripple {
            display: inline-block;
            position: relative;
            width: 80px;
            height: 80px;
        }
        .lds-ripple div {
            position: absolute;
            border: 4px solid #fff;
            opacity: 1;
            border-radius: 50%;
            animation: lds-ripple 1s cubic-bezier(0, 0.2, 0.8, 1) infinite;
        }
        .lds-ripple div:nth-child(2) {
            animation-delay: -0.5s;
        }
        @keyframes lds-ripple {
            0% {
                top: 36px;
                left: 36px;
                width: 0;
                height: 0;
                opacity: 1;
            }
            100% {
                top: 0px;
                left: 0px;
                width: 72px;
                height: 72px;
                opacity: 0;
            }
        }

    }
}

</style>