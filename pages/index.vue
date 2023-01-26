<template lang="pug">
.main
  VModal
  VHero
  VCollections
  VQuality
  VTeam



 
</template>

<script>
import VHero from '@/components/main/VHero.vue';
import VCollections from '@/components/main/VCollections.vue';
import VQuality from '@/components/main/VQuality.vue';
import VTeam from '@/components/main/VTeam.vue';
import VModal from '@/components/VModal.vue';
export default {
  components: {
    VHero, VCollections,VQuality,VTeam,VModal
  },
    
   
    
}
</script>

<style lang="scss" scoped>

</style>