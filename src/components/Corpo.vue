<template>
    <div class="corpo">
      <div id="head">
        <FontAwesomeIcon icon="fa-brands fa-spotify" class="icona"/>
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
#head{
  background-color: #2e3a46;
  height: 70px;
  .icona{
    float: left;
    color: green;
    font-size: 46px;
    margin: 12px;
  }
}

#canzoni {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  background-color: #1e2d3b;
  padding: 50px 340px 50px 340px;
  gap: 30px;
  min-height: 759px;
  height: 100%;
}
</style>
  