<template>
  <div id="app">
    <!-- Header -->
    <Header @choice="searchGenre" />
    <!-- Main Content -->
    <Main :disc="disk" />
    
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    
  },
  data() {
        return {
            disk: [],
        };
    },
    created() {
        this.getDisk();
    },
    methods: {
        getDisk() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(result => {
                this.disk = result.data.response;
            })
            .catch(err => console.log(err));
        },
        searchGenre() {
          console.log('Emit event');
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
@import '@/styles/vars.scss';
@import '~bootstrap/scss/bootstrap.scss'

</style>
