
<template>
  <div class="cover-card">
      <div class="copertina">
          <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="poster">
      </div>
      <h2>New Jersey</h2>
      <span>Bon Jovi</span>
      <span>1988</span>
  </div>
</template>

<script>
export default {
    name: 'Card'
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
    color: #7D776E;
    background-color: #2D3C47;
    @include center(sinistra);
    flex-direction: column;
    .copertina{
        margin: 15px 0px 10px 0px;
        width: 80%;
    }
    h2{
        margin-bottom: 15px;
        color: #fff;
    }
}

</style>