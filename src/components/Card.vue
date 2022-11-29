<template>
    <div class="card">
      <div class="immagine">{{branoInfo.poster}}</div>
      <div class="titolo">{{branoInfo.title}}</div>
      <div class="artista">{{branoInfo.author}}</div>
      <div class="genere">{{branoInfo.genre}}</div>
      <div class="anno">{{branoInfo.year}}</div>
    </div>
</template>
  
<script>
export default {
  name: 'cartaCanzone',
  props: {
    branoInfo: Object,
  }
}
</script>
  
<!-- css-->
<style scoped lang="scss">
  
</style>
  