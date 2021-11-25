<template>
    <div class="my-card">
        <img :src="image" alt="title" />
        <h3>{{ title }}</h3>
        <h4>{{ subtitle }}</h4>
        <h4>{{ addInfo }}</h4>
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
    },

};
</script>

<style scoped lang="scss">

</style>