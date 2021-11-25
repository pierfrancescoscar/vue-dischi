<template>
  <main>
      <section class="container">
          <div v-if="disk.length > 0" class="row">
              <div v-for="(element, index) in disk" :key="`item-${index}`" class="col-6">
                <Card 
                    :image="disk.poster"
                    :title="disk.title"
                    :subtitle="disk.author"
                    :addInfo="disk.year"
                    :addInfo2="disk.genre"
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
                this.disk = result.data;
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
}
</style>