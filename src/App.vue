<template>
  <div id="app">
    <!-- Header -->
    <Header />
    
  </div>
</template>

<script>
import Header from '@/components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
    
  }
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
@import '@/styles/vars.scss';
@import '~bootstrap/scss/bootstrap.scss'

</style>
