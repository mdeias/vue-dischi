<template>
  <main>
      <div class="contenitore">
          <Card/>
      </div>
  </main>
</template>

<script>
import Card from './Card';
export default {
    name: 'Main',
    components:{
        Card
    }
}
</script>

<style lang="scss">
@import '../assets/style/generali.scss';
@import '../assets/style/utilities.scss';
@import '../assets/style/mixins.scss';

main{
    background-color: #1E2C3B;
    height: calc(100vh - 50px);
}

</style>