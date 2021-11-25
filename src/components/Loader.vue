<template>
    <div class="loader w-100 h-100 d-flex flex-column justify-content-center align-items-center p-5">
        <div class="loader-text">
            <h3 class="text-center mb-3">Best albums are coming...</h3>
        </div>

        <svg 
            xmlns="http://www.w3.org/2000/svg" 
            fill="currentColor" 
            class="bi bi-clock" 
            viewBox="0 0 16 16"
            >
            <path d="M8 3.5a.5.5 0 0 0-1 0V9a.5.5 0 0 0 .252.434l3.5 2a.5.5 0 0 0 .496-.868L8 8.71V3.5z"/>
            <path d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm7-8A7 7 0 1 1 1 8a7 7 0 0 1 14 0z"
        />
        </svg>

         <div class="loader-text">
            <h3 class="text-center mt-3">Wait for it...</h3>
        </div>

    </div>
</template>

<script>
export default {
    name: 'Loader',

}
</script>

<style scoped lang="scss">
.loader {
    position: fixed;
    top: 0;
    left: 0;
    background-color: lightcoral;
    
    svg {
        width: 30%;
    }

}

</style>