<template>
  <div id="app">
    <!-- Header -->
    <Header @choice="searchGenre" />
    <!-- Main Content -->
    <Main :disc="filteredGenre" />
    
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
            genreChoice: '',
        };
    },
    computed: {
      filteredGenre() {
        if(this.genreChoice === '') {
          return this.disk;
        }
        return this.disk.filter(item => {
          return item.genre.toLowerCase().includes(this.genreChoice.toLowerCase())
        })
      }
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
        searchGenre(el) {
          // console.log('Emit event');
          this.genreChoice = el;
          console.log(this.genreChoice)
        }
    }
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
@import '@/styles/vars.scss';
@import '~bootstrap/scss/bootstrap.scss'

</style>
