<template lang="pug">
.page
    .header
        VHeader
        .main
            .container
                nuxt
    .footer
        VFooter

    
</template>

<script>
import VHeader from '../components/VHeader.vue';
import VFooter from '../components/VFooter.vue';
    export default {
        components: {
            VHeader,VFooter
        },
        
    }
</script>

