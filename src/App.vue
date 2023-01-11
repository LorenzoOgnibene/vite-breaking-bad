<script >
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';
  export default{
    components:{
      AppHeader,
      AppMain,
    }
  }
</script>
  
<template>
  <header>
    <AppHeader />
  </header>

  <main>
    <AppMain />
  </main>
  
</template>

<style lang="scss">
  @use './style/general.scss' as*;
  @use './style/variables'as*;
  @import 'bootstrap/scss/bootstrap.scss';

</style>
