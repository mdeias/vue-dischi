<template>
  <main>
      <div class="contenitore">
          <Card
          v-for="card in carte"
          :key="card.id"
          />
      </div>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './Card';

export default {
    name: 'Main',
    components:{
        Card
    },

    data(){

        return{
            carte: [],    
        }

    },

    methods:{
        getApi(){
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then(r => {
                    
                    this.carte = r.data.response;
                    console.log(this.carte);
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
    background-color: #1E2C3B;
    padding: 72px;
    .contenitore{
        @include center (between);
        flex-wrap: wrap;
    }
}

</style>