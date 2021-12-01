<template>
  <header>
      <img src="../assets/img/logo-spotify.png" alt="">
      <select 
      v-model="genere"
      @change="cambiaGenere"
      >
          <option value="" selected>Seleziona genere</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Metal">Metal</option>
          <option value="Jazz">Jazz</option>
      </select>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            genere:'',
        }
    },
    methods:{
        cambiaGenere(){
           
            console.log('Header.vue sta facendo partire un evento', this.genere);
            this.$emit('newSelect', this.genere);
        }
    }
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