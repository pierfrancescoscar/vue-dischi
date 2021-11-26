<template>
  <main class="p-5">
      <section class="container">
          <div v-if="disc.length > 0" class="row justify-content-center">
              <div class="my-column text-center mb-4" v-for="(element, index) in disc" :key="`item-${index}`">
                <Card 
                    :image="element.poster"
                    :title="element.title"
                    :subtitle="element.author"
                    :addInfo="element.year"
                    :addInfo2="element.genre"
                 />
              </div>

          </div>
                <Loader v-else />
      </section>
  </main>
</template>

<script>

import Card from '@/components/Card.vue';
import Loader from '@/components/Loader.vue';

export default {
    name: 'Main',
    components: {
        Card,
        Loader,
    },
    props: {
        disc: Array,
    },

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