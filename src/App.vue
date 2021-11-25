<template>
  <div id="app">
    <!-- Header -->
    <Header />
    <!-- Main Content -->
    <Main />
    
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import Card from '@/components/Card.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Card,
    
  }
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
@import '@/styles/vars.scss';
@import '~bootstrap/scss/bootstrap.scss'

</style>
