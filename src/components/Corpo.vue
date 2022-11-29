<template>
    <div class="corpo">
      <div id="head">
        
      </div>
      <div id="canzoni">
        <cartaCanzone
          v-for="brano in arrMusic"
          :branoInfo="brano"
          :key="brano.title"
        />
      </div>
    </div>
</template>
  
<script>
import cartaCanzone from '@/components/Card.vue'

export default {
  name: 'corpoPage',
  components: {
    cartaCanzone,
  },
  props: {
    arrMusic: Array,
  }
}
</script>
  
<!-- css-->
<style scoped lang="scss">
  
</style>
  