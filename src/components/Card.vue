<template>
    <div class="my-card text-center p-3 h-100">
        <img class="w-75 mb-2" :src="image" :alt="title" />
        <h3 class="h5">{{ title }}</h3>
        <h4 class="h6">{{ subtitle }}</h4>
        <h4 class="h6">{{ addInfo }}</h4>
        <h5 class="h6">{{ addInfo2 }}</h5>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        title: String,
        subtitle: String,
        addInfo: String,
        addInfo2: String,
    }

}
</script>

<style scoped lang="scss">
@import '@/styles/vars.scss';

.my-card {
    background-color: #2e3a46;
}
    h3 {
        color: white;
    }

    h4 {
        color: $subtitle-color;
    }

    h5 {
        color: white;
    }
</style>