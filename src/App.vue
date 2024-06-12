<template>
  <div id="app">
    <AppHeader />
    <AppMain />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
    }
  }
}
</script>

<style lang="scss">
  @use './styles/general.scss';
  @use './node_modules/bootstrap/scss/bootstrap.scss';
  @use './styles/partials/mixins' as *;
  @use './styles/partials/variables' as *;

  body{
    background-color: #d48f38;
  }
  
</style>
