
<template>
  <div class="cover-card">
      <div class="copertina">
          <img :src="card.poster" :alt="card.title">
      </div>
      <h4>{{card.title.toUpperCase()}}</h4>
      <span>{{card.author}}</span>
      <span class="year">{{card.year}}</span>
  </div>
</template>

<script>
export default {
    name: 'Card',
    props:{
        card: Object
    }
}
</script>

<style lang="scss">

@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';

.cover-card{
    height: 270px;
    width: 17%;
    margin: 20px 5px 20px 5px;
    padding: 10px;
    color: #7D776E;
    background-color: #2D3C47;
    @include center(sinistra);
    flex-direction: column;
    text-align: center;
    .copertina{
        margin: 15px 0px 10px 0px;
        width: 90%;
    }
    h4{
        margin-bottom: 15px;
        color: #fff;
    }
    .year{
        margin-top: 2px;
        font-size: 11px;
    }
}

</style>