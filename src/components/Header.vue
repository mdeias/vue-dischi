<template>
  <header>
      <img src="../assets/img/logo-spotify.png" alt="">
  </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss">
@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';

header{
    @include center(sinistra);
    height: 50px;
    background-color: #2D3C47;
    padding-left: 10px;
    img{
        width: 35px;
    }
}

</style>