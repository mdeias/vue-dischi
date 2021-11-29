<template>
  <div class="search">
      <input
      v-model="testoUtente"
      @keyup.enter="$emit('inviaRicerca',testoUtente)"
      type="text" placeholder="Search">
      <button
      @click="$emit('inviaRicerca',testoUtente)">
      Cerca
      </button>
      <button @click="reset">
        Reset
      </button>
  </div>
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
      return{
        testoUtente:''
      }
    },
    methods:{
      reset(){
        this.testoUtente = '';
        this.$emit('inviaRicerca',this.testoUtente);
      }
    }
}
</script>

<style lang="scss">
@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';
.search{
  position: absolute;
  top: -35px;
  right: 40px;
  width: 250px;
  @include center(between);
  input{
    font-size: 10px;
    
    padding: 2px 10px;
    width: 200px;
    border-radius: 5px;
  }
  button{
    font-size: 10px;
    padding: 2px 6px
  }
}


</style>