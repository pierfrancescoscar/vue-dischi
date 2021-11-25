<template>
  <main class="p-5">
      <section class="container">
          <div v-if="disk.length > 0" class="row justify-content-center">
              <div class="my-column text-center mb-4" v-for="(element, index) in disk" :key="`item-${index}`">
                <Card 
                    :image="element.poster"
                    :title="element.title"
                    :subtitle="element.author"
                    :addInfo="element.year"
                    :addInfo2="element.genre"
                 />
              </div>

          </div>
          <div v-else>Loading...</div>
      </section>
  </main>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue';

export default {
    name: 'Main',
    components: {
        Card,
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
        }
    }

}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';

main {
    background-color: $bg-color;
    height: 100vh;
}
    .my-column {
        width: calc(100% / 8);
        
    }
</style>