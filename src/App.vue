<template>
  <div>
    <Header/>
    <Main/>
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
